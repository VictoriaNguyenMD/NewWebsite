<template>
  <div class="wrapper">
    <q-layout view="lHh Lpr lFf">
      <q-toolbar>
        <q-toolbar-title> Victoria Nguyen </q-toolbar-title>

        <div class="gt-sm">
          <q-btn
            flat
            v-for="item in essentialLinks"
            :key="item.title"
            text-transform="uppercase"
            ><a :href="item.link">{{ item.title }}</a>
          </q-btn>
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
        <div>
          <!-- <RenderSVG
            v-for="item in socialMediaList"
            :key="item.icon"
            v-bind="item"
          /> -->
        </div>
      </q-footer>
    </q-layout>
  </div>
</template>

<style lang="scss">
@import "../css/app.scss";
</style>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "src/components/EssentialLink.vue";
import RenderSVGVue from "src/components/RenderSVG.vue";

const socialMediaList = [
  {
    icon: "src/assets/facebook.svg",
    link: "https://www.facebook.com/profile.php?id=100009945305694",
  },
  // {
  //   icon: "https://www.instagram.com/victorianguyen.md/",
  //   link: "https://twitter.com/MedInnovatorMD",
  // },
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
    // RenderSVG,
  },

  setup() {
    return {
      essentialLinks: dropdownList,
      renderSVG: socialMediaList,
    };
  },
});
</script>
