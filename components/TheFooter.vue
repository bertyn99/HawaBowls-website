<template>
  <footer class="w-full bg-primary-500">
    <div class="md:container mx-auto py-4">
      <div class="flex flex-col justify justify-between items-center">
        <base-circle-logo></base-circle-logo>
        <div class="sm:flex sm:justify-around text-center">
          <nuxt-link to="/" class="footer-link">Accueil</nuxt-link>
          <nuxt-link to="#menu" class="footer-link">Menu</nuxt-link>
          <nuxt-link to="/blog" class="footer-link">Blog</nuxt-link>
          <nuxt-link to="/contact" class="footer-link">Contact</nuxt-link>

          <nuxt-link to="/cgu" class="footer-link">Cgu</nuxt-link>
          <nuxt-link to="/cgv" class="footer-link">Cgv</nuxt-link>
          <!--  <nuxt-link to="/contact" class="footer-link"> Traiteur</nuxt-link> -->
        </div>
        <div>
          <button-network
            name="facebook"
            url="https://www.facebook.com/hawabowls"
          ></button-network>
          <button-network
            name="instagram"
            url="https://www.instagram.com/hawa_bowls/"
          ></button-network>
        </div>
        <div>
          <span class="text-gray-300"
            ><i class="fa fa-copyright" aria-hidden="true"
              >Copyright Hawabowls</i
            ></span
          >
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import CircleLogo from "./BaseCircleLogo.vue";
import ButtonNetwork from "./ButtonNetwork.vue";
export default {
  components: { CircleLogo, ButtonNetwork },
  name: "TheFooter"
};
</script>

<style>
.footer-link {
  @apply block text-white text-xl font-semibold mx-2 hover:text-accent-500 rounded sm:text-gray-100 px-2 py-1 sm:inline-block;
}
</style>
