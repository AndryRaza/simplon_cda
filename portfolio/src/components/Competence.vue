<template>
  <section class="container-fluid my-5" id="competences">
    <h2 class="text-center">Mes compétences</h2>
    <div class="row row-cols-md-2 row-cols-1">
      <div class="col">
        <h2 class="text-center">Domaines de compétences</h2>

        <div
          class="text-center d_comp"
          v-for="(competence, index) in competences"
          v-bind:key="index"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="16"
            fill="currentColor"
            class="bi bi-gear-fill"
            viewBox="0 0 16 16"
          >
            <path
              d="M9.405 1.05c-.413-1.4-2.397-1.4-2.81 0l-.1.34a1.464 1.464 0 0 1-2.105.872l-.31-.17c-1.283-.698-2.686.705-1.987 1.987l.169.311c.446.82.023 1.841-.872 2.105l-.34.1c-1.4.413-1.4 2.397 0 2.81l.34.1a1.464 1.464 0 0 1 .872 2.105l-.17.31c-.698 1.283.705 2.686 1.987 1.987l.311-.169a1.464 1.464 0 0 1 2.105.872l.1.34c.413 1.4 2.397 1.4 2.81 0l.1-.34a1.464 1.464 0 0 1 2.105-.872l.31.17c1.283.698 2.686-.705 1.987-1.987l-.169-.311a1.464 1.464 0 0 1 .872-2.105l.34-.1c1.4-.413 1.4-2.397 0-2.81l-.34-.1a1.464 1.464 0 0 1-.872-2.105l.17-.31c.698-1.283-.705-2.686-1.987-1.987l-.311.169a1.464 1.464 0 0 1-2.105-.872l-.1-.34zM8 10.93a2.929 2.929 0 1 1 0-5.86 2.929 2.929 0 0 1 0 5.858z"
            />
          </svg>
          <strong class="competences_titre">
            {{ competence.title }}
          </strong>
          <p class="text-white competences_text">
            <span v-for="(competence,index)  in competence.competences" :key="index">
                {{competence}}
              <br />
            </span>
          </p>
        </div>
      </div>
      <div class="col">
        <h2 class="text-center">Compétences en développement</h2>

        <div class="row row-cols-md-3 row-cols-3 mt-5 mb-3">
          <div class="col text-center mb-md-5">
            <img src="../assets/html-5.png" height="80px" width="80px" />
          </div>
          <div class="col text-center mb-md-5">
            <img src="../assets/css.png" height="80px" width="80px" />
          </div>
          <div class="col text-center mb-md-5">
            <img
              class="mt-2"
              src="../assets/js.png"
              height="80px"
              width="80px"
            />
          </div>
          <div class="col text-center mt-md-5">
            <img
              class="mt-2"
              src="../assets/php.png"
              height="80px"
              width="80px"
            />
          </div>
          <div class="col text-center mt-md-5">
            <img
              class="mt-2"
              src="../assets/python.png"
              height="80px"
              width="80px"
            />
          </div>
          <div class="col text-center mt-md-5">
            <img
              class="mt-2"
              src="../assets/bootstrap.png"
              height="80px"
              width="80px"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Competence",
  data: function () {
    return {
      competences: [
        {
          title: "Intégration HTML5, CSS et Javascript",
          competences: [
            "Mise en forme de pages web",
            "Interactivité avec l'interface",
            "Déclinaison du site pour mobiles et tablettes",
          ],
        },
        {
          title: "Programmation côté serveur",
          competences: [
            "Échanges d'informations",
            "Stockage dans une base de données",
            "Ébauche de MCD",
            "Ajax",
          ],
        },
        {
          title: "Gestion de sites web",
          competences: [
            "Wireframes / Maquettage",
            "Hébergement de sites web/applications web",
            "Versioning via GitHub",
            "Référencement",
          ],
        },
        {
          title: "Conception d'applications web",
          competences: [
            "Mise en place d'un panel d'administration",
            "Gestion de fichiers, utilisateurs inscrits",
            "CRUD",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>

#competences{
    background: #3F353A;
background: -moz-linear-gradient(45deg, #3F353A 0%, #C4C7CB 53%, #FFFFFF 100%);
background: -webkit-linear-gradient(45deg, #3F353A 0%, #C4C7CB 53%, #FFFFFF 100%);
background: linear-gradient(45deg, #3F353A 0%, #C4C7CB 53%, #FFFFFF 100%);
-webkit-box-shadow: 5px 5px 12px 9px #000000; 
box-shadow: 5px 5px 12px 9px #000000;
}

#competences > h2 {
    font-size:40px;
}

</style>