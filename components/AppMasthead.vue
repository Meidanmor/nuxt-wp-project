<template>
<section class="masthead hero">
<div class="stars">
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
</div>

<div class="max-width">
<h2> 
{{tagline}}
</h2>

<div class="heroBTNS">
<a href="javascript:void(0)" class="magnetic showProjects"> PORTFOLIO </a>
<a href="javascript:void(0)" class="magnetic startProject"> START NOW </a>
</div>

</div>
</section>
</template>

<script>
export default {
  data() {
    return {
      tagline: "אנחנו לא בונים אתרים ,אנחנו מגשימים חלומות!"
    };
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/mixins.scss";
section.hero {
.stars {
    position: absolute;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    top: 0;
    left: 0;
}
h2{
    font-family: 'Rubik Dirt';
    font-weight: 400;
    margin: 0 0 40px;
    letter-spacing: 0px;
    font-size: 64px;
    max-width: 700px;
    color: #fff;
}
.heroBTNS {
    margin-top: 20px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}
a{
    text-decoration: none;
    height: 64px;
    font-size: 18px;
    width: 200px;
    display: flex;
    max-width: 49%;
    font-family: 'ClashDisplay-Medium';
    align-items: center;
    justify-content: center;
}
}
section.masthead {
  width: 100%;
  height: 90vh;
  overflow: hidden;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 7vw;
  background: -moz-radial-gradient(
      center,
      ellipse cover,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0) 37%,
      rgba(0, 0, 0, 0.65) 100%
    ),
    url("/mountains-masthead.jpg") no-repeat center center scroll; /* FF3.6-15 */
  background: -webkit-radial-gradient(
      center,
      ellipse cover,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0) 37%,
      rgba(0, 0, 0, 0.65) 100%
    ),
    url("/mountains-masthead.jpg") no-repeat center center scroll; /* Chrome10-25,Safari5.1-6 */
  background: radial-gradient(
      ellipse at center,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0) 37%,
      rgba(0, 0, 0, 0.65) 100%
    ),
    url("/mountains-masthead.jpg") no-repeat center center scroll; /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
  background-size: cover;
  color: #333;
  h1 {
    color: white;
    @include fluid-type(font-size, 320px, 1366px, 30px, 65px);
  }
}
</style>
