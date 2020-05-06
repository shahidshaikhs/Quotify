<template>
  <div>
    <transition name="bounce">
      <div class="alert" v-if="alertVisible">
        <p>Yay! Quote copied to clipboard!</p>
      </div>
    </transition>
    <div class="container-3">
      <input
        v-model="searchText"
        class="search-input"
        type="text"
        placeholder="Filter using author name"
      />
    </div>
    <div class="container">
      <main>
        <div
          v-for="(quote, index) in filterQuotes"
          :key="index"
          class="card"
          @click="doCopy(quote.quote, quote.author)"
        >
          <p>{{quote.quote}}</p>
          <h2>{{quote.author}}</h2>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import quotesJSON from "../json/quotes.json";
import authorJSON from "../json/authors.json";

export default {
  name: "Home",
  data() {
    return {
      quotes: quotesJSON,
      authors: authorJSON,

      quotesList: [],
      searchText: "",
      alertVisible: false
    };
  },
  computed: {
    filterQuotes() {
      return this.quotesList.filter(quote => {
        var totalMatches = 0;
        var searchTerm = this.searchText
          .toLowerCase()
          .trim()
          .split(" ");
        for (let i = 0; i < searchTerm.length; i++) {
          if (
            quote.author.toLowerCase().includes(searchTerm[i].toLowerCase())
          ) {
            totalMatches++;
          }
        }
        return totalMatches == searchTerm.length;
      });
    }
  },
  methods: {
    getInitialQuotesList() {
      for (let i = 0; i < this.quotes.length; i++) {
        this.quotesList.push({
          quote: this.quotes[i].quote,
          author: this.authors[this.quotes[i].authorIndex].name
        });
      }
    },
    doCopy(quote, author) {
      let self = this;
      let copyText = quote + " - " + author
      this.$copyText(copyText).then(
        function() {
          self.alertVisible = true;
          setTimeout(function() {
            self.alertVisible = false;
          }, 2000);
        },
        function() {
          alert("Can not copy");
        }
      );
    }
  },
  beforeMount() {
    this.getInitialQuotesList();
  }
};
</script>
<style>
.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
