<template>
  <section
    class="d-flex flex-column justify-content-center align-items-center"
    id="accueil"
  >
    <img
      class="px-5"
      src="../assets/pp.png"
      alt="photo"
      height="250px"
      id="photo_profil"
    />
    <div class="mt-5 text-center p-5" id="presentation">
      <p style="font-size: 30px; color: red">
        <span
          >En recherche d'alternance en tant que développeur web Fullstack</span
        >
      </p>
      <h1>Andry RAZAFINDRAZAKA</h1>
      <h2>@Jeune développeur web FullStack</h2>
      <p class="p-3">
        Développeur web Fullstack actuellement en formation chez Simplon, je
        suis
        <strong
          >à la recherche d'une
          <br />
          alternance au sein d'une entreprise </strong
        >pour pouvoir continuer ma formation à partir de Mai.
        <br />
        <strong class="mt-5"
          >N'hésitez pas à me suivre et à me contacter sur les réseaux sociaux.
   
        </strong>
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: "Accueil"
};
</script>


<style scoped>
#accueil {
  background: #ffffff;
  background: -moz-linear-gradient(top, #ffffff 0%, #ffffff 50%, #141414 100%);
  background: -webkit-linear-gradient(
    top,
    #ffffff 0%,
    #ffffff 50%,
    #141414 100%
  );
  background: linear-gradient(to bottom, #ffffff 0%, #ffffff 50%, #141414 100%);
  height: 100vh;
}

#photo_profil {
  margin-bottom: -70px;
  background-color: white;
  z-index: 1;
}

#presentation{
    border:2px solid black;
}
</style>
