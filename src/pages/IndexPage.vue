<template>
  <q-page class="flex flex-center">
    <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    />
    <div><UserLogin></UserLogin></div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import UserLogin from "../components/UserLogin.vue";

export default defineComponent({
  name: "IndexPage",
  components: { UserLogin },
});
</script>
