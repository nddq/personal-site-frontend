<template>
  <v-app>
    <v-app-bar
      app
      :color="$vuetify.theme.dark ? `#121212` : 'white'"
    >
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn class="custom-btn" flat tile text @click="$vuetify.goTo('#about-me')">About me</v-btn>
        <v-btn class="custom-btn v2" flat tile text @click="$vuetify.goTo('#projects')">Projects</v-btn>
        <v-btn flat tile icon @click="toggleTheme()"><v-icon>mdi-lightbulb-outline</v-icon></v-btn>
      </v-toolbar-items>
      <v-spacer></v-spacer>
    </v-app-bar>
    <v-main>
      <section id="top">
        <v-parallax
          :height="350"
          src="https://i.redd.it/n3cfog1e3bh51.jpg"
        >
        </v-parallax>
      </section>
      <section id="about-me">
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">ABOUT ME</h2>

          <v-responsive
            class="mx-auto mb-8"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>
            <v-divider></v-divider>
          </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Hello! My name is Quang Nguyen. I'm currently a Junior at Boston University majoring in Computer Science with a minor in Linguistics.
          </v-responsive>

          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img src="https://lh3.googleusercontent.com/a-/AOh14GjXS3WslCNa-YGsVscu1XHFy-N1MwGzs8JLImeKqQ"></v-img>
          </v-avatar>

          <div></div>
          <v-row align="center"
                 class="white--text mx-auto"
                 justify="center"
          >
            <v-tooltip bottom v-for="link in links" :key="link.title" color="#00b8ff">
              <template v-slot:activator="{ on, attrs }">
              <v-btn class="ma-2" flat tile large icon :href="link.href" v-bind="attrs" v-on="on">
                  <v-icon>{{link.icon}}</v-icon>
              </v-btn>
              </template>
              <span>{{link.title}}</span>
            </v-tooltip>
          </v-row>
        </v-container>

        <div class="py-12"></div>
      </section>
      <section id="mid">
        <v-parallax
          :height="400"
          src="https://i.redd.it/n3cfog1e3bh51.jpg"
        >
        </v-parallax>
      </section>
      <section id="projects">
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">Projects</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>
        </v-container>
        <div class="py-12"></div>
      </section>
      <section id="bot">
        <v-parallax
          :height="400"
          src="https://i.redd.it/n3cfog1e3bh51.jpg"
        >
        </v-parallax>
      </section>
    </v-main>
    <v-footer
      class="justify-center"
      color="#121212"
      height="80"
    >
      <div class="title font-weight-light grey--text text--lighten-1 text-center">
        &copy; {{ (new Date()).getFullYear() }} — Vuetify, LLC — Artwork by u/Zman20201
      </div>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  },
  data() {
    return {
      links: [
        {
          title: "Github",
          icon: "mdi-github",
          href: "https://github.com/nddq"
        },
        {
          title: "LinkedIn",
          icon: "mdi-linkedin",
          href: "https://www.linkedin.com/in/nddq/"
        },
        {
          title: "Mail",
          icon: "mdi-gmail",
          href: "mailto:nddq@bu.edu"
        },
        {
          title: "Resume",
          icon: "mdi-file-document",
          href: "https://nddq-resume.s3.us-east-2.amazonaws.com/Quang_Nguyen_Resume.pdf"
        },
      ]
    }
  }
};
</script>
<style scoped>

.custom-btn {
  background: linear-gradient(#00b8ff, #00b8ff) bottom / 0 .2em no-repeat;
	transition: 0.3s background-size;
}
.custom-btn.v2{
  background: linear-gradient(#FF00CC, #FF00CC) bottom / 0 .2em no-repeat;
}

.custom-btn:hover {
  background-size: 100% .2em;
}

.theme--light.v-divider {
    border-color: #00b8ff !important; 
}
.theme--dark.v-divider {
    border-color: #00b8ff !important; 
}
</style>
