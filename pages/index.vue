<template>
  <div>
    <app-masthead></app-masthead>
    
<section class="PROJECTS">
<div class="max-width">

    <ul class="theProjects">
    
        <li class="post" v-for="post in posts" :key="post.id">
        <div class="postImgWrap">
         <span class="text front">{{ post.title.rendered }}</span>
         <span class="text back">{{ post.title.rendered }}</span>
         <div class="magnetic theImage">
       <nuxt-link :to="`blog/${post.slug}`" class="readmore slide">
          צפייה בפרויקט
</nuxt-link>
<div class="hideOverflow">
          <img :src="post.images.large" width="500" height="500"/>
          </div>
          </div>
        </div>

</li>

    </ul>
  </div>
  </section>
  </div>
</template>

<script>
import AppMasthead from "@/components/AppMasthead.vue";
export default {
  components: {
    AppMasthead
  },
  data() {
    return {
      selectedTag: null,
      activeClass: "active"
    };
  },
  computed: {
    posts() {
      return this.$store.state.posts;
    },
  },
  created() {
    this.$store.dispatch("getPosts");
  },
  methods: {

  }
};
</script>

<style lang="scss">
section{
min-height: 100vh;
}
section.PROJECTS{
.max-width{
    display: flex;
    flex-direction: column;
    align-items: center;
}
ul.theProjects {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    width: 100%;
    margin-top: 80px;
}
ul.theProjects li {
    position: relative;
    width: 100%;
    padding-right: 25%;
    margin-bottom: 230px;
    counter-increment: section;
    height: 600px;
}
.postImgWrap {
    position: relative;
    align-items: flex-end;
    height: 95%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
span.text {
    -webkit-text-stroke: 1px #fff;
    font-size: 110px;
    background: transparent;
    position: absolute;
    top: 0;
    left: 0;
    color: transparent;
    font-weight: bold;
    padding: 10px;
    display: inline-block;
    width: -webkit-fill-available;
}
span.text.front {
    z-index: 2;
}
span.text.back {
    z-index: 0;
color: #fff;
}
.theImage {
    width: 100%;
    height: 100%;
    position: relative;
    transition: 1s ease;
    transform-origin: right;
    transform-style: preserve-3d;
}
.Open{
position: absolute;
    z-index: 9;
    bottom: 50px;
    right: -75px;
    font-size: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 150px;
    height: 150px;
    border: 2px solid #fff;
    animation: 4.5s linear rotation infinite;
text-align: center;
    text-decoration: none;
    line-height: 1;
    background: transparent;
    border-radius: 50%;
    padding: 15px;
}
.hideOverflow {
    height: inherit;
    overflow: hidden;
}
img {
    width: 100%;
    background: #000;
    z-index: 1;
    height: 100%;
    object-fit: cover;
}
}
.posts {
  display: grid;
  grid-template-columns: 2fr 1fr;
  grid-template-rows: 1fr;
  grid-column-gap: 6vw;
  margin: 5em auto;
  max-width: 80vw;
}

main {
  grid-area: 1 / 1 / 2 / 2;
}

aside {
  grid-area: 1 / 2 / 2 / 3;
}

h2 {
  margin-bottom: 2em;
}

a,
a:active,
a:visited {
  text-decoration: none;
  color: black;
}

a.readmore {
  display: inline-block;
  font-size: 11px;
  text-transform: uppercase;
  padding: 5px 15px;
  letter-spacing: 2px;
  position: relative;
  color: #000;
  font-weight: 700;
  font-family: "Open Sans", serif;
  border: 1px solid #ccc;
  background: #fff;
}

.tags-title {
  background-color: #000;
  color: #fff;
  border: none;
  text-transform: capitalize;
  letter-spacing: 0;
  font-size: 1.2rem;
  padding: 15px;
  margin: 0 35px;
  position: relative;
  top: -25px;
}

.tags-list {
  background: #f5f5f5;
  padding: 70px 25px 25px;
  margin-top: -65px;
}

.post {
  border-bottom: 1px solid rgb(223, 222, 222);
  margin-bottom: 2em;
  padding-bottom: 2em;
  color: #444;

  h3 {
    margin-bottom: 0.5em;
    font-size: 26px;
  }
}

.tags-list ul {
  padding-left: 0;
}

.tags-list li {
  font-family: "Open Sans", serif;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 6px 15px;
  margin: 0 0 10px 10px;
  display: inline-block;
  font-size: 0.7rem !important;
  border: 1px solid #000;
  transition: all 0.3s;
  outline: none;
  font-weight: normal;
  cursor: pointer;
  background: #fff;
  a {
    color: #000;
  }
}

.active {
  border: 1px solid #d44119;
  background-color: #fae091 !important;
}

.slide {
  position: relative;
  background: transparent;
  -webkit-transition: 0.3s ease;
  transition: 0.3s ease;
  z-index: 1;
  backface-visibility: hidden;
  perspective: 1000px;
  transform: translateZ(0);
  cursor: pointer;

  &:hover {
    color: #fff;
  }

  &:hover:before {
    right: -1px;
  }
}

.slide::before {
  content: "";
  display: block;
  position: absolute;
  background: #000;
  transition: right 0.3s ease;
  z-index: -1;
  top: -2px;
  bottom: -2px;
  left: -2px;
  right: 108%;
  backface-visibility: hidden;
}
</style>
