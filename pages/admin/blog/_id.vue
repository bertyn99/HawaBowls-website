<template>
  <main>
    <div class="relative bg-secondary-500 md:pt-32 pb-32 pt-12"></div>
    <section class=" relative  px-4 md:px-10 mx-auto w-full -m-24">
      <!-- This example requires Tailwind CSS v2.0+ -->
      <div class="bg-white rounded p-2 shadow-md">
        <form
          enctype="multipart/form-data"
          class="space-y-8 divide-y divide-gray-200"
          @submit.prevent="update"
        >
          <div class="space-y-8 divide-y divide-gray-200 sm:space-y-5">
            <div>
              <div class="flex justify-between">
                <div>
                  <h3 class="text-lg leading-6 font-medium text-gray-900">
                    Details de l'article
                  </h3>
                  <p class="mt-1 max-w-2xl text-sm text-gray-500">
                    Infos sur l'article
                  </p>
                </div>

                <button
                  @click="destroyArticle"
                  type="button"
                  class="ml-3 inline-flex justify-center items-center py-1 px-4 border border-transparent shadow-sm text-sm font-semibold rounded-md text-white bg-red-600 hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                >
                  Supprimer
                </button>
              </div>
              <div class="pt-8 space-y-6 sm:pt-10 sm:space-y-5">
                <div class="space-y-6 sm:space-y-5">
                  <div
                    class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-start sm:border-t sm:border-gray-200 sm:pt-5"
                  >
                    <label
                      for="first_name"
                      class="block text-sm font-medium text-gray-700 sm:mt-px sm:pt-2"
                    >
                      Titre de l'article
                    </label>
                    <div class="mt-1 sm:mt-0 sm:col-span-2">
                      <input
                        v-model="article.title"
                        type="text"
                        name="title"
                        id="title"
                        autocomplete="title"
                        class="max-w-lg block w-full shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:max-w-xs sm:text-sm border-gray-300 rounded-md"
                      />
                    </div>
                  </div>
                  <div
                    class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-start sm:border-t sm:border-gray-200 sm:pt-5"
                  >
                    <label
                      for="first_name"
                      class="block text-sm font-medium text-gray-700 sm:mt-px sm:pt-2"
                    >
                      Auteur de l'article
                    </label>
                    <div class="mt-1 sm:mt-0 sm:col-span-2">
                      <input
                        v-model="article.author"
                        type="text"
                        name="title"
                        id="title"
                        autocomplete="title"
                        class="max-w-lg block w-full shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:max-w-xs sm:text-sm border-gray-300 rounded-md"
                      />
                    </div>
                  </div>
                  <div
                    class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-start sm:border-t sm:border-gray-200 sm:pt-5"
                  >
                    <label
                      for="country"
                      class="block text-sm font-medium text-gray-700 sm:mt-px sm:pt-2"
                    >
                      Description
                    </label>
                    <div class="mt-1 sm:mt-0 sm:col-span-2">
                      <textarea
                        v-model="article.desc"
                        id="about"
                        name="about"
                        rows="3"
                        class="max-w-lg shadow-sm block w-full focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm border border-gray-300 rounded-md"
                      ></textarea>
                    </div>
                  </div>

                  <div class="pt-6 sm:pt-5 sm:border-t border-gray-300 ">
                    <div role="group" aria-labelledby="label-email">
                      <div
                        class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-baseline"
                      >
                        <div>
                          <div
                            class="text-base font-medium text-gray-900 sm:text-sm sm:text-gray-700"
                            id="label-email"
                          >
                            Publication
                          </div>
                        </div>
                        <div class="mt-4 sm:mt-0 sm:col-span-2">
                          <div class="max-w-lg space-y-4">
                            <div>
                              <div class="relative flex items-start">
                                <div class="flex items-center h-5">
                                  <input
                                    v-model="article.isPublished"
                                    id="offers"
                                    name="offers"
                                    type="checkbox"
                                    class="focus:ring-indigo-500 h-4 w-4 text-indigo-600 border-gray-300 rounded"
                                  />
                                </div>
                                <div class="ml-3 text-sm">
                                  <label
                                    for="offers"
                                    class="font-medium text-gray-700"
                                    >Publié</label
                                  >
                                </div>
                              </div>
                              <div class="relative flex items-start">
                                <div class=" text-sm">
                                  <label
                                    for="offers"
                                    class="font-medium text-gray-700"
                                    >Date de Publication</label
                                  >
                                </div>
                                <div class="flex items-center h-5">
                                  {{ article.publishingDate }}
                                </div>
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="mt-6 sm:mt-5 space-y-6 sm:space-y-5">
                <div
                  class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-start sm:border-t sm:border-gray-200 sm:pt-5"
                >
                  <label
                    for="cover_photo"
                    class="block text-sm font-medium text-gray-700 sm:mt-px sm:pt-2"
                  >
                    Photo article
                  </label>
                  <div class="mt-1 sm:mt-0 sm:col-span-2">
                    <div
                      class="max-w-lg flex justify-center px-6 pt-5 pb-6 border-2 border-gray-300 border-dashed rounded-md"
                    >
                      <upload-cloudinary :nb="1"></upload-cloudinary>
                    </div>
                  </div>
                </div>
                <div
                  class="sm:grid sm:grid-cols-3 sm:gap-4 sm:items-start sm:border-t sm:border-gray-200 sm:pt-5"
                >
                  <label
                    for="about"
                    class="block text-sm font-medium text-gray-700 sm:mt-px sm:pt-2"
                  >
                    Content
                  </label>
                  <div
                    class="mt-1 sm:mt-0 sm:col-span-3 bg-white shadow-md rounded-lg"
                  >
                    <client-only>
                      <editor-wyg v-model="article.content" />
                    </client-only>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="pt-5">
            <div class="flex justify-end">
              <nuxt-link :to="{ name: 'admin-blog' }">
                <button
                  type="button"
                  class="bg-white py-2 px-4 border border-gray-300 rounded-md shadow-sm text-sm font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                >
                  Retour
                </button></nuxt-link
              >
              <button
                type="submit"
                class="ml-3 inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-primary-600 hover:bg-primary-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
              >
                Sauvegarder
              </button>
            </div>
          </div>
        </form>
      </div>
      <footer-admin></footer-admin>
    </section>
  </main>
</template>

<script>
import { mapActions } from "vuex";
import UploadCloudinary from "~/components/admin/UploadCloudinary.vue";
import EditorWyg from "~/components/blog/EditorWyg.vue";
export default {
  layout: "admin",
  components: { EditorWyg, UploadCloudinary },
  data() {
    return {
      article: {},
      oldArt: {}
    };
  },
  methods: {
    ...mapActions({
      getArticle: "blog/getArticle",
      updateArticle: "blog/updateArticle",
      deleteArticle: "blog/deleteArticle"
    }),
    async update() {
      try {
        let response = await this.updateArticle({
          id: this.$route.params.id,
          article: this.article
        });
        console.log(response);
        //rajoute notification reussite et echec
        this.$router.push("/admin/blog");
      } catch (e) {
        console.log(e);
      }
    },
    async destroyArticle() {
      try {
        let response = await this.deleteArticle({
          id: this.$route.params.id
        });
        console.log(response);
        //rajoute notification reussite et echec
        this.$router.push("/admin/blog");
      } catch (e) {
        console.log(e);
      }
    }
  },
  async fetch() {
    this.article = await this.getArticle(this.$route.params.id);
    this.oldArt = { ...this.article };
  },
  watch: {
    /* ingredient: {
      handler: function(val) {
        console.log(
          val.name == this.oldIng.name &&
            val.type == this.oldIng.type &&
            val.isInStock === this.oldIng.isInStock
        );
        if (
          val.name != this.oldIng.name ||
          val.type != this.oldIng.type ||
          val.isInStock !== this.oldIng.isInStock
        ) {
          this.change = true;
        } else {
          this.change = false;
        }
      },
      deep: true */
  }
};
</script>

<style></style>
