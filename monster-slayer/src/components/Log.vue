<template>
  <transition name="fade">
    <section class="row log">
      <div class="small-12 columns">
        <ul>
          <transition-group name="fade">
            <li
              v-for="log in logs"
              :class="{'player-turn': log.isPlayer, 'monster-turn': !log.isPlayer}"
              :key="log"
            >{{ log.message }}</li>
          </transition-group>
        </ul>
      </div>
    </section>
  </transition>
</template>

<script>
export default {
  name: "Log",
  props: ["logs"]
};
</script>

<style>
.log ul {
  list-style: none;
  font-weight: bold;
  text-transform: uppercase;
}
.log ul li {
  margin: 5px;
}
.log ul .player-turn {
  color: blue;
  background-color: #e4e8ff;
}
.log ul .monster-turn {
  color: red;
  background-color: #ffc0c1;
}
.fade-enter {
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 500ms;
}
</style>
