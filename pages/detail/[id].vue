<script setup>
const route = useRoute();
console.log(route.params.id);
const { data: film } = await useFetch(
  "http://www.omdbapi.com/?apiKey=41243417&i=" + route.params.id
);
</script>

<template>
  <section id="detail" class="pt-36 mb-20">
    <div class="container">
      <div class="flex">
        <div class="md:w-1/3">
          <img :src="film.Poster" alt="" />
        </div>
        <div class="md:w-2/3">
          <h1 class="text-4xl mb-6">{{ film.Title }}</h1>
          <table class="border-collapse">
            <!-- <thead>
              <tr>
                <th class="p-2">Kolom 1</th>
                <th class="p-2">Kolom 2</th>
              </tr>
            </thead> -->
            <tbody >
              <tr>
                <td class="p-2 align-top">Rilis</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Year }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Rating</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.imdbRating }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Genre</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Genre }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Actors</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Actors }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Writer</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Writer }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Language</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Language }}</td>
              </tr>
              <tr>
                <td class="p-2 align-top">Plot</td>
                <td class="p-2 align-top">:</td>
                <td class="p-2 align-top">{{ film.Plot }}</td>
              </tr>
              <!-- Tambahkan baris data lainnya sesuai kebutuhan -->
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>
