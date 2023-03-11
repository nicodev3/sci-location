<template>
  <div>
    <the-header></the-header>
    <main class="max-w-7xl mx-auto px-5 lg:px-0">
      <section class="py-10">
        <header class="mb-10">
          <h1 class="mb-5 text-2xl font-bold">
            Cabinet de consultation à louer en plein cœur du centre-ville de Sceaux
          </h1>
          <p>
            Psychologue partage cabinet de consultation situé à SCEAUX (92) dans la partie piétonne de la rue Houdan.
          </p>
          <p>C’est dans ce quartier extrêmement recherché que se situe le Cabinet.
            <span class="font-semibold">Idéalement situé dans la rue piétonne</span>, proche des commerces et des écoles, le cabinet saura vous séduire grâce à une pièce principale spacieuse et lumineuse, qui donne sur la rue Houdan via deux grandes fenêtres. La pièce principale, chaleureuse et confortable, comprend quatre fauteuils, un canapé, un bureau et des chaises.</p>
        </header>

        <div class="lg:flex lg:gap-8 mb-10">
          <div class="lg:w-1/2">
            <!-- https://github.com/lukaszflorczak/vue-agile -->
            <agile class="main" ref="main" :options="options1" :as-nav-for="asNavFor1">
              <div class="slide" v-for="(slide, index) in slides" :key="index" :class="`slide--${index}`">
                <img :src="slide" class="w-full h-full object-cover"/>
              </div>
            </agile>
            <agile class="thumbnails" ref="thumbnails" :options="options2" :as-nav-for="asNavFor2">
              <div class="slide slide--thumbniail mt-2" v-for="(slide, index) in slides" :key="index" :class="`slide--${index}`" @click="$refs.thumbnails.goTo(index)">
                <img :src="slide"/>
              </div>
              <template slot="prevButton"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path d="m10.5 16 1-1-7-7 7-7-1-1-8 8 8 8z"/></svg></template>
              <template slot="nextButton"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16"><path d="m5.5 0-1 1 7 7-7 7 1 1 8-8-8-8z"/></svg></template>
            </agile>
          </div>
          <div class="lg:w-1/2">
            <h2>SCEAUX - Appartement centre ville - Cabinet de consultation</h2>
            <h2 class="mb-5 text-lg">
              Appartement de 35m2, équipé pour toutes professions libérales (psychologue, sophrologue, nutritionniste, réflexologue...).
            </h2>
            <p>L’appartement, d’une surface totale de 35 m2, est équipé en double vitrage, pour une meilleure isolation thermique et phonique. Une petite entrée, dotée d’un placard, fait le lien entre la pièce principale et les pièces d’eau (salle de bain et toilettes à part).
              Une cuisine, séparée et entièrement équipée, est mise à votre disposition. Le chauffage électrique permet de maintenir une température agréable en toute autonomie.</p>
            <p>Le cabinet est également doté du wifi pour les personnes qui en ont besoin.
              L’entrée sécurisée dans l’immeuble se fait grâce à un digicode.</p>
            <p class="mb-8">
              Indépendance totale des autres praticiens, tout l'appartement est dédié à la consultation.
            </p>

            <ul class="chips flex gap-4 mb-8">
              <li>35 m <sup>2</sup></li>
              <li>1 pièce</li>
              <li>cuisine aménagée</li>
              <li>SDB</li>
              <li>toilettes</li>
            </ul>

            <ul class="chips flex gap-4 flex-wrap">
              <li>wi-fi</li>
              <li>digicode</li>
              <li>ménage + charges compris</li>
            </ul>
          </div>
        </div>
        <div class="mb-10">
          <h2>
            Clin d’œil sur la rue Houdan, rue piétonne de Sceaux
          </h2>
          <p>
            En plein cœur de ville, la rue piétonne de Sceaux est la principale voie publique des Scéens. Commerçants de bouche, services en tout genre, écoles, maison des jeunes et de la culture, animations à chaque saison... Tous les piétons de Sceaux ou d’ailleurs aiment flâner devant les vitrines des boutiques, se retrouver entre amis ou s’asseoir en terrasse le temps d’un thé ou d’un café.
          </p>
          <p>
            Ce secteur historique, débarrassé de la circulation automobile, est bien connu et apprécié de tous. Cette pépite de la Ville représente une véritable réussite, tant pour ses habitants que pour le développement commerçant et culturel. A Sceaux, tout le monde le sait : « la rue Houdan, c’est là qu’il faut être ! ».
          </p>
          <p>
            Facilement accessible par les transports en commun, la priorité est donnée aux piétons et aux cyclistes, pour lesquels de nombreux aménagements de stationnement sont prévus.
          </p>
        </div>
      </section>
    </main>
    <the-footer></the-footer>
  </div>
</template>
<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      asNavFor1: [],
      asNavFor2: [],
      options1: {
        dots: false,
        fade: true,
        navButtons: false
      },

      options2: {
        autoplay: true,
        centerMode: true,
        dots: false,
        navButtons: false,
        slidesToShow: 3,
        responsive: [
          {
            breakpoint: 600,
            settings: {
              slidesToShow: 5
            }
          },

          {
            breakpoint: 1000,
            settings: {
              navButtons: true
            }
          }
        ]
      },

      slides: [
        require('assets/photo-1.jpg'),
        require('assets/photo-2.jpg'),
      ]
    }
  },
  mounted () {
    this.asNavFor1.push(this.$refs.thumbnails)
    this.asNavFor2.push(this.$refs.main)
  }
}
</script>
<style>
body {
  font-family: Quicksand, sans-serif;
}

h1, h2 {
  font-family: "Playfair Display", serif;
}

h2 {
  @apply font-semibold text-2xl mb-5;
}

p {
  @apply mb-5;
}

.chips li {
  @apply border border-red-500 bg-neutral-50 rounded p-2;
}

.slide--thumbniail {
  margin-right: 10px;
}

.agile__nav-button--prev,
.agile__nav-button--next {
  position: absolute;
  bottom: 40px;
}

.agile__nav-button--prev {
  left: -1rem;
}

.agile__nav-button--next {
  right: 1rem;
}

</style>
