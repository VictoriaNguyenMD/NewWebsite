<template>
  <div class="wrapper">
    <q-layout view="lHh Lpr lFf">
      <q-toolbar>
        <q-toolbar-title> Victoria Nguyen </q-toolbar-title>

        <div class="gt-sm">
          <q-btn flat label="ABOUT" />
          <q-btn flat label="ARTICLES" />
          <q-btn flat label="BOOKS" />
          <q-btn flat label="INSTAGRAM" />
        </div>

        <div class="lt-md">
          <q-btn flat icon="menu">
            <q-menu>
              <EssentialLink
                v-for="item in essentialLinks"
                :key="item.title"
                v-bind="item"
              />
            </q-menu>
          </q-btn>
        </div>
      </q-toolbar>
      <q-page-container>
        <router-view />
      </q-page-container>
      <q-footer>
        <div>© Victoria Nguyen 2022. Built using Quasar. Hosted on GitHub.</div>
        <div></div>
      </q-footer>
    </q-layout>
  </div>
</template>

<style lang="scss">
@import "../css/app.scss";
</style>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

const socialMediaList = [
  {
    icon: "img:../assets/twitter.svg",
    link: "https://www.facebook.com/profile.php?id=100009945305694",
  },
  {
    icon: "https://www.instagram.com/victorianguyen.md/",
    link: "https://twitter.com/MedInnovatorMD",
  },
];

const dropdownList = [
  {
    title: "About",
    link: "https://quasar.dev",
  },
  {
    title: "Articles",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Book Notes",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Instagram",
    link: "https://forum.quasar.dev",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
  },

  setup() {
    return {
      essentialLinks: dropdownList,
    };
  },
});
</script>
