<template>
  <b-row style="margin-left: 0;margin-right: 0;">
    <b-col md="4">
      <b-img
        :src="avatar"
        id="avatar-img"
        alt="Shaxriyor"
        @mouseenter="changeAvatar"
        @mouseleave="changeAvatar"
      />
    </b-col>

    <b-col md="8">
      <h2 class="intro animate__animated animate__fadeInUp animate__fast">
        Hi 👋,
        <br />I<span>'m Shaxriyor&nbsp;Qobiljonov</span>.
      </h2>

      <div class="col-md-10 info">
        A <b>front-end developer</b> and <b>technical writer</b> passionate
        about solving problems with tech.<br />
        I am skilled with building exceptional <b>websites</b> and
        <b>mobile applications</b>, and currently i'm exploring the AI
        (Artificial Intelligence) ecosystem.
        <br />
        <b-button
          class="action-btn animate__animated animate__wobble animate__delay-4s animate__fast"
          to="/projects"
        >
          Explore >
        </b-button>

        <b-button class="action-btn" to="/contact" variant="primary">
          Get In Touch
        </b-button>

        <!-- .SOCIAL LINKS SECTION -->
        <div
          class="social-icons animate__animated animate__fadeInUp animate__delay-1s"
        >
          <social-link :to="socialLinks.instagram">
            <InstagramIcon />
          </social-link>

          <social-link :to="socialLinks.github">
            <GithubIcon />
          </social-link>

          <social-link :to="socialLinks.twitter">
            <TwitterIcon />
          </social-link>

          <social-link :to="socialLinks.facebook">
            <FacebookIcon />
          </social-link>

          <social-link :to="socialLinks.mail">
            <MailIcon />
          </social-link>

          <social-link :to="socialLinks.youtube">
            <YoutubeIcon />
          </social-link>
        </div>
      </div>
    </b-col>
  </b-row>
</template>

<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import TwitterIcon from "vue-ionicons/dist/logo-twitter.vue";
import InstagramIcon from "vue-ionicons/dist/logo-instagram.vue";
import FacebookIcon from "vue-ionicons/dist/logo-facebook.vue";
import YoutubeIcon from "vue-ionicons/dist/logo-youtube.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";

export default {
  components: {
    GithubIcon,
    TwitterIcon,
    InstagramIcon,
    FacebookIcon,
    YoutubeIcon,
    MailIcon
  },

  data() {
    return {
      avatar: require("@/assets/avatar-1.webp"),
      socialLinks: {
        github: "https://github.com/1Shox",
        twitter: "https://x.com/1Shaxriyor1515",
        facebook: "https://www.facebook.com/profile.php?id=100089110770746",
        instagram: "https://www.instagram.com/1shox_1515/",
        mail: "mailto:info4a.elijah@gmail.com",
      }
    };
  },

  head: {
    title: "Portfolio ⚡  - Shaxriyor",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Asaolu Elijah is an awesome front-end developer and technical writer, passionate about building solutions that works across multiple platforms with high accessibility approach. Elijah has vast knowledge in web development with over 3+ years experience in building actual products"
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Portfolio ⚡ - Shaxriyor"
      },
      {
        property: "og:description",
        content:
          "Asaolu Elijah is an awesome front-end developer and technical writer, passionate about building solutions that works across multiple platforms with high accessibility approach. Elijah has vast knowledge in web development with over 3+ years experience in building actual products"
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/coding.png")
      }
    ]
  },
  methods: {
    changeAvatar() {
      if (this.avatar == require("@/assets/avatar-2.webp")) {
        this.avatar = require("@/assets/avatar-1.webp");
      } else {
        this.avatar = require("@/assets/avatar-2.webp");
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();

      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  }
};
</script>
