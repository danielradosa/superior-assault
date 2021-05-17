<template>
  <div>
    <div class="bottom">
      <h2>
        <span>SUPERIOR ASSAULT</span> JE KOLEKTÍV DIZAJNÉROV
        A DEVELOPEROV, KTORÝCH NAPADLO VYTVORIŤ VLASTNÚ ZNAČKU.
        TAKTIEŽ MÁME V OBĽUBE MEMES LMAO.
      </h2>
    </div>

    <div class="links">
      <div class="bot-left">
        <h3>Stalkuj nás</h3>
        <a href="https://www.facebook.com/superiorassault" target="_blank"
          ><i class="fab fa-facebook"></i
        ></a>
        <a href="https://www.instagram.com/superior_assault/" target="_blank"
          ><i class="fab fa-instagram"></i
        ></a>
      </div>

      <div class="bot-right">
        <h3>Odporúčané čítanie</h3>
        <hr />
        <router-link @click.native="scrollToTop" to="/Terms"
          >Podmienky & pravidlá</router-link
        >
        
      </div>
    </div>

    <footer>
      <h4>&copy; COPYRIGHT - DANIEL RADOSA 2069 - All Lefts Reversed</h4>
      <a href="#"><button class="fa fa-caret-up"></button></a>
    </footer>
  </div>
</template>

<script>
export default {
  methods: {
    scrollToTop() {
      window.scrollTo(0, 0);
    },
  },
};
</script>

<style lang="scss" scoped>
  .fa-caret-up {
    border:none;
    background-color: #108071;
    color: white;
    width: 3em;
    height: 3em;
    border-radius: 4em;
    margin-top: 1.5em;
  }
</style>
