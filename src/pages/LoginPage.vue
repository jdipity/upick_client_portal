<template>
  <q-page class="flex flex-center">
    <div><UserLogin></UserLogin></div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import UserLogin from "../components/UserLogin.vue";

export default defineComponent({
  name: "LoginPage",
  components: {
    UserLogin,
  },
});
</script>
