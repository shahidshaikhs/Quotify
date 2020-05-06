<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";

export default {
  data() {
    return {};
  },
  components: {
    Navbar
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Karla:wght@400;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Rock+Salt&display=swap");
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  -webkit-box-sizing: inherit;
  box-sizing: inherit;
  color: #373d49;
}

body {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  font-family: "Karla", sans-serif;
  line-height: 1.7;
}

.container {
  padding: 2.5rem 1rem;
}

.container-2 {
  padding: 0rem 1rem;
}

.container-3 {
  margin-top: 0.5rem;
  padding: 0rem 1rem;
}

nav {
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  z-index: 10;
  background-color: white;
}

nav h1 {
  font-size: 14px;
  letter-spacing: 2px;
  font-family: "Rock Salt", cursive;
}

nav button {
  border: none;
  background: none;
  cursor: pointer;
  opacity: 0.8;
  margin-left: auto;
  outline: none;
  -webkit-tap-highlight-color:  rgba(255, 255, 255, 0);
}

nav button:active span{
  background-color: #03A9F4;
}

nav button,
nav ul {
  margin-left: auto;
}

nav button:hover {
  opacity: 1;
}

nav button span {
  height: 3px;
  background-color: #444444;
  width: 20px;
  display: block;
  margin-top: 4px;
  border-radius: 20px;
}

nav button span:first-child {
  width: 15px;
  margin-left: 5px;
}

nav button span:last-child {
  width: 15px;
}

nav ul {
  display: none;
}

nav ul li {
  display: inline-block;
}

nav ul li a {
  font-size: 14px;
  text-transform: uppercase;
  text-decoration: none;
  margin-left: 2rem;
  font-weight: bold;
  letter-spacing: 2px;
  position: relative;
}

nav ul li a::after {
  content: "";
  position: absolute;
  z-index: -1;
  top: 60%;
  left: -0.1em;
  right: -0.1em;
  bottom: 0;
  transition: top 200ms cubic-bezier(0, 0.8, 0.13, 1);
  background-color: #b3e5fc;
}

nav ul li a:hover::after {
  top: 0%;
}

.responsive-nav {
  position: absolute;
  top: -20%;
  background-color: white;
  width: 100%;
  -webkit-box-shadow: 0px 2px 5px rgba(34, 34, 34, 0.075);
  box-shadow: 0px 2px 5px rgba(34, 34, 34, 0.075);
  -webkit-transition: all 500ms ease-out;
  transition: all 500ms ease-out;
  z-index: 1;
}

.responsive-nav li a {
  display: block;
  text-align: center;
  text-decoration: none;
  margin: 2rem 0;
  text-transform: uppercase;
  font-size: 12px;
  letter-spacing: 2px;
  font-weight: bold;
    -webkit-tap-highlight-color:  rgba(255, 255, 255, 0);
}

.responsive-nav-active {
  top: 10% !important;
}

header p {
  font-size: 18px;
}

.instructions {
  font-size: 14px;
  margin-top: 5px;
}

main {
  -moz-column-width: 14em;
  -webkit-column-width: 14em;
  -moz-column-gap: 1em;
  -webkit-column-gap: 1em;
  transition: all 200ms linear;
}

.card {
  display: inline-block;
  margin: 0.5rem 0;
  padding: 1.5rem 1rem;
  width: 100%;
  border: 2px solid #dbe1ef;
  border-radius: 15px;
  -webkit-transition: all 200ms linear;
  transition: all 200ms linear;
}

.card p {
  font-size: 1.2rem;
}

.card h2 {
  font-size: 1rem;
  margin-top: 10px;
}

.card:hover {
  -webkit-transform: scale(1.02);
  transform: scale(1.02);
  border: 2px solid #35a4ff;
  cursor: pointer;
}

.search-input {
  margin-top: 20px;
  font-size: 14px;
  padding: 10px 20px;
  border: 2px solid #dbe1ef;
  border-radius: 50px;
  outline: none;
}

.search-input:focus {
  border: 2px solid #35a4ff;
}

.alert {
  position: fixed;
  bottom: 0;
  left: 50%;
  transform: translate(-50%);
  background-color: #03a9f4;
  margin-bottom: 20px;
  padding: 6px 15px;
  border-radius: 50px;
  width: 80%;
  -webkit-box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
  -moz-box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
  box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
}

.alert p {
  color: white;
}

@media (min-width: 1024px) {
  nav button,
  .responsive-nav {
    display: none;
  }
  nav ul {
    display: block;
  }
  .container {
    padding: 2.5rem 10rem;
  }
  .container-2 {
    padding: 0rem 10rem;
  }
  .container-3 {
    margin-top: 0.1rem;
    padding: 0rem 10rem;
  }

  .alert {
    position: fixed;
    width: fit-content;
    bottom: 0;
    left: 50%;
    transform: translate(-50%);
    background-color: #03a9f4;
    margin-bottom: 20px;
    padding: 10px 20px;
    border-radius: 50px;
    -webkit-box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
    -moz-box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
    box-shadow: 0px 15px 35px -12px rgba(0, 38, 109, 0.5);
  }

  .link {
    font-size: 18px;
    text-decoration: none;
    position: relative;
  }
  .link::after {
    content: "";
    position: absolute;
    z-index: -1;
    top: 60%;
    left: -0.1em;
    right: -0.1em;
    bottom: 0;
    transition: top 200ms cubic-bezier(0, 0.8, 0.13, 1);
    background-color: #b3e5fc;
  }

  .link:hover::after {
    top: 0%;
  }
}
</style>
