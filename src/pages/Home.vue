<template>
  <main class="home space">
    <img
      id="logo"
      src="https://user-images.githubusercontent.com/18376481/78156268-78aed080-7436-11ea-9da7-57d83ec5ec8a.png"
      alt="logos of Vue, Netlify and Fauna"
    />
    <h1 style="text-align:center">Peacewater information tree tool</h1>
    <h2>ecocommunity@protonmail.com</h2>
    <ul>
      <li><a href=https://sharaj2.sg-host.com/forum>Peacewater project planning forum</a>
      <li><a href=https://scdhub.org/forum>Searchable Database</a>
    </ul>

    <div>
      <p>
       Using Faunadb and Netlify for free 😎
      </p>

      <p>
        
        <a href="https://github.com/chiubaca/vue-netlify-fauna-starter-kit"
          >source code</a
        >
 
      </p>
    </div>
    <LoginSignup v-if="currentUser === null" />
    <div v-else id="greeting">
      <h2>🖐️ Welcome Back {{ currentUser.user_metadata.full_name }}!</h2>
      <p>
        You're logged in. Go check out your
        <router-link :to="{ name: 'journals' }">journals ➡️ </router-link>.
      </p>
    </div>
    <GithubCorner
      url="https://github.com/chiubaca/vue-netlify-fauna-starter-kit"
    />
  </main>
</template>

<script>
import { mapGetters } from "vuex";
import LoginSignup from "../components/LoginSignup.vue";
import GithubCorner from "../components/GithubCorner.vue";

export default {
  name: "Home",
  components: {
    LoginSignup,
    GithubCorner
  },
  props: {
    msg: String
  },
  data() {
    return {};
  },
  computed: {
    ...mapGetters("auth", ["currentUser"])
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#greeting {
  border-style: dashed;
  padding: 15px;
  border-radius: 15px;
  border-color: #c6c6c6;
  border-width: 1px;
  h2 {
    text-transform: capitalize;
  }
}
img#logo {
  width: 100%;
  height: auto;
}
</style>
