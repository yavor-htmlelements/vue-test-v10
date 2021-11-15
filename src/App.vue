<template>
  <div class="root">
    <smart-menu id="menu">
      <smart-menu-item value="Sun">
        <img class="img1" src="./assets/logo.png" title="Sun" />Sun
      </smart-menu-item>
      <smart-menu-items-group>
        <img class="img2" src="./assets/logo.png" title="Planets" />Planets
        <smart-menu-item value="Earth">
          <img src="./assets/logo.png" title="Earth" />Earth
        </smart-menu-item>
        <smart-menu-item value="Mars">
          <img src="./assets/logo.png" title="Mars" />Mars
        </smart-menu-item>
      </smart-menu-items-group>
      <smart-menu-item value="Moon">
        <img class="img3" src="./assets/logo.png" title="Moon" />Moon
      </smart-menu-item>
    </smart-menu>

    <div class="content">
        <smart-tree id="tree">
        <smart-tree-items-group>
          <i class="material-icons"></i> Attractions
          <smart-tree-item>Movies</smart-tree-item>
          <smart-tree-item>Circus</smart-tree-item>
          <smart-tree-item>Concerts</smart-tree-item>
          <smart-tree-item>Monuments</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Dining
          <smart-tree-item>Restaurants</smart-tree-item>
          <smart-tree-item>Cafés</smart-tree-item>
          <smart-tree-item>Bars</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Education
          <smart-tree-item>Schools</smart-tree-item>
          <smart-tree-item>Colleges</smart-tree-item>
          <smart-tree-item>Universities</smart-tree-item>
          <smart-tree-item>Educational courses</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Family
          <smart-tree-item>Babysitting</smart-tree-item>
          <smart-tree-item>Family trips</smart-tree-item>
          <smart-tree-item>Theme parks</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Health
          <smart-tree-item>Hospitals</smart-tree-item>
          <smart-tree-item>Family physicians</smart-tree-item>
          <smart-tree-item>Optics</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Office
          <smart-tree-item>Offices for rent</smart-tree-item>
          <smart-tree-item>Office equipment</smart-tree-item>
          <smart-tree-item>Repair works</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Promotions
          <smart-tree-item>Sales</smart-tree-item>
          <smart-tree-item>Malls</smart-tree-item>
          <smart-tree-item>Collective buying</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Radio
          <smart-tree-item>Available stations</smart-tree-item>
          <smart-tree-item>Search</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Recipes
          <smart-tree-item>With meat</smart-tree-item>
          <smart-tree-item>With fish</smart-tree-item>
          <smart-tree-item>Vegetarian recipes</smart-tree-item>
          <smart-tree-item>Vegan recipes</smart-tree-item>
          <smart-tree-item>Desserts</smart-tree-item>
          <smart-tree-item>Chef's recommendations</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Sports
          <smart-tree-item>Football</smart-tree-item>
          <smart-tree-item>Basketball</smart-tree-item>
          <smart-tree-item>Tennis</smart-tree-item>
          <smart-tree-item>Baseball</smart-tree-item>
          <smart-tree-item>Cycling</smart-tree-item>
        </smart-tree-items-group>
        <smart-tree-items-group>
          <i class="material-icons"></i> Travel
          <smart-tree-item>Local destinations</smart-tree-item>
          <smart-tree-item>Book tickets</smart-tree-item>
          <smart-tree-item>Organised travel</smart-tree-item>
        </smart-tree-items-group>
    </smart-tree>
    <div class="screen"></div>
    </div>
  </div>
</template>

<script>
import { onMounted } from "vue";
import "smart-webcomponents/source/styles/smart.default.css";
import "smart-webcomponents/source/modules/smart.menu.js";
import "smart-webcomponents/source/modules/smart.tree.js";
export default {
  name: "app",
  setup() {
    onMounted(() => {
      const menu = document.getElementById("menu");
      menu.addEventListener("itemClick", function(event) {
        window.open(
          "https://en.wikipedia.org/wiki/" + event.detail.value,
          "_blank"
        );
      });
    });
  }
};
</script>

<style>
  @font-face {
    font-family: "Material Icons";
    font-style: normal;
    font-weight: 400;
    src: url(https://fonts.gstatic.com/s/materialicons/v31/2fcrYFNaTjcS6g4U3t-Y5ZjZjT5FdEJ140U2DJYC3mY.woff2)
      format("woff2");
  }

  .material-icons {
    font-family: "Material Icons";
    font-weight: normal;
    font-style: normal;
    font-size: inherit;
    line-height: 1;
    letter-spacing: normal;
    text-transform: none;
    display: inline-block;
    white-space: nowrap;
    word-wrap: normal;
    direction: ltr;
    -webkit-font-feature-settings: "liga";
    -webkit-font-smoothing: antialiased;
  }

  smart-tree {
    width: 50%;
    height: auto;
  }
  smart-tree i {
    margin-right: 8px;
  }

  img {
    margin-right: 7px;
    width: 50px;
  }
  smart-menu {
    width: 100%;
    height: 70px;
  }
  .content{
    display: flex;
  }
  .screen{
    width: 50%;
    height: 400px;
    background-color: lightgrey;
  }

  @media only screen and (max-width: 700px) {
    smart-tree {
      width: 50%;
      height: 50%;
    }
    body,
    html {
      width: 100%;
      height: 100%;
    }
    .img1,
    .img2,
    .img3 {
            visibility:hidden;
            display: flex;
            z-index: 99999999999;
          }
    smart-menu {
        height: 50px!important;
    }
    smart-menu-item:hover .img1,
    smart-menu-item:hover .img2,
    smart-menu-item:hover .img3
      {
          visibility: visible;
          margin-top: 20px;
          border: solid black 1px;
          position: fixed;
      }
  }
</style>