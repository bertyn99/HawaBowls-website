<template>
  <main>
    <div class="relative bg-secondary-500 md:pt-32 pb-32 pt-12"></div>
    <section class=" relative  px-4 md:px-10 mx-auto w-full -m-24">
      <!-- This example requires Tailwind CSS v2.0+ -->
      <div class="bg-white rounded p-2 shadow-md">
        <form
          class="space-y-8 divide-y divide-gray-200"
          @submit.prevent="create"
        >
          <div class="space-y-8 divide-y divide-gray-200 sm:space-y-5">
            <div>
              <div>
                <h3 class="text-lg leading-6 font-medium text-gray-900">
                  Details de l'article
                </h3>
                <p class="mt-1 max-w-2xl text-sm text-gray-500">
                  Infos sur l'article
                </p>
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
                      <div class="space-y-1 text-center">
                        <svg
                          class="mx-auto h-12 w-12 text-gray-400"
                          stroke="currentColor"
                          fill="none"
                          viewBox="0 0 48 48"
                          aria-hidden="true"
                        >
                          <path
                            d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02"
                            stroke-width="2"
                            stroke-linecap="round"
                            stroke-linejoin="round"
                          />
                        </svg>
                        <div class="flex text-sm text-gray-600">
                          <label
                            for="file-upload"
                            class="relative cursor-pointer bg-white rounded-md font-medium text-indigo-600 hover:text-indigo-500 focus-within:outline-none focus-within:ring-2 focus-within:ring-offset-2 focus-within:ring-indigo-500"
                          >
                            <span>Upload a file</span>
                            <input
                              id="file-upload"
                              name="file-upload"
                              type="file"
                              class="sr-only"
                            />
                          </label>
                          <p class="pl-1">or drag and drop</p>
                        </div>
                        <p class="text-xs text-gray-500">
                          PNG, JPG, GIF up to 10MB
                        </p>
                      </div>
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
                :disabled="!valid"
                :class="[!valid ? 'opacity-50' : 'opacity-100']"
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
import EditorWyg from "~/components/blog/EditorWyg.vue";
export default {
  layout: "admin",
  components: { EditorWyg },
  data() {
    return {
      article: {
        title: "",
        author: "",
        isPublished: false,
        desc: "",
        content: "",
        publishingDate: "",
        cover: []
      },
      oldArt: {}
    };
  },
  methods: {
    ...mapActions({
      createArticle: "blog/createArticle"
    }),
    async create() {
      try {
        let response = await this.createArticle({
          article: this.article
        });
        console.log(response);
        //rajoute notification reussite et echec
        /*   this.$router.push("/admin/blog"); */
      } catch (e) {
        console.log(e);
      }
    }
  },
  computed: {
    valid() {
      return (
        this.article.title &&
        this.article.desc &&
        this.article.author &&
        this.article.content
      );
    }
  }
};
</script>
