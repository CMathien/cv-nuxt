<template>
  <v-app light>

    <!--En-tête-->

    <v-parallax
      src="https://images.pexels.com/photos/2457317/pexels-photo-2457317.png?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
      height="350"
      class="animate__animated animate__fadeIn"
    >
      <v-row>
        <v-col class="col-4 d-flex align-center justify-end">
          <v-avatar color="cyan" size="150" class="ml-5">
            <v-img
              :src="require('assets/profil.png')"
              aspect-ratio="1"
              class="photo animate__animated animate__flipInY"
            >
            </v-img>
          </v-avatar>
        </v-col>
        <v-col class="m-5 d-flex flex-column justify-center">
          <h1
            class="text-h2 font-weight-light text-uppercase animate__animated animate__bounce"
          >
            Camille Mathien
          </h1>
          <h2 class="text-h4 font-weight-light">
            Future développeuse web
            <span id="spin"></span>
          </h2>
        </v-col>
      </v-row>
    </v-parallax>

    <!--Timelines-->

    <v-sheet light tile>
      <v-card-title class="text-h4 font-weight-light mb-4 justify-center"
        ><span><v-icon color="cyan" class="mx-2">mdi-briefcase</v-icon></span
        >Expériences professionnelles et formations<span
          ><v-icon color="pink" class="mx-2">mdi-school</v-icon></span
        ></v-card-title
      >
      <v-timeline :dense="$vuetify.breakpoint.smAndDown">
        <v-timeline-item
          v-for="(year, i) in years"
          :key="i"
          :color="year.color"
          fill-dot
        >
          <v-card class="mx-10 animate__animated animate__fadeInUp">
            <v-card-title :class="year.color">
              <v-icon class="mx-2" dark>{{ year.icon }}</v-icon>
              <h2 class="text-h6 white--text font-weight-light">
                {{ year.year }}
              </h2>
            </v-card-title>
            <v-container>
              <h2
                :class="`headline font-weight-light mb-4 ${year.color}--text`"
              >
                {{ year.title }}
              </h2>
              {{ year.text }}
            </v-container>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </v-sheet>

    <!--Séparation visuelle-->

    <v-parallax
      src="https://images.pexels.com/photos/2457317/pexels-photo-2457317.png?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
      height="100"
      class="animate__animated animate__fadeIn"
    >
    </v-parallax>

    <!--Compétences-->

    <v-sheet light tile width="60%" class="mx-auto">
      <v-card-title class="text-h4 font-weight-light mb-4 justify-center"
        ><v-icon
          class="mdi mdi-medal-outline mr-10"
          aria-hidden="true"
          color="black"
        ></v-icon
        >Compétences</v-card-title
      >
      <v-card-text align="center">
        <v-progress-circular :size="70" :width="7" color="pink" :value="60"
          ><v-icon color="#e44d26" title="HTML5"
            >mdi-language-html5</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="60"
          ><v-icon color="#264de4" title="CSS3"
            >mdi-language-css3</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="50"
          ><v-icon color="#f7df1e" title="JavaScript"
            >mdi-language-javascript</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="30"
          ><v-icon color="#DD0031" title="Angular"
            >mdi-angular</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="30"
          ><v-icon color="#108775" title="Nuxt.js"
            >mdi-nuxt</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="50"
          ><v-icon color="#6610f2" title="Bootstrap"
            >mdi-bootstrap</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="50"
          ><v-icon color="#1697f6" title="Vuetify"
            >mdi-vuetify</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="10"
          ><v-icon color="#CF649A" title="Sass"
            >mdi-sass</v-icon
          ></v-progress-circular
        >
        <v-progress-circular :size="70" :width="7" color="pink" :value="5"
          ><v-icon color="#777bb3" title="PHP"
            >mdi-language-php</v-icon
          ></v-progress-circular
        >
      </v-card-text>
      <v-alert
        width="60vw"
        justify="center"
        align="center"
        class="mx-auto"
        border="top"
        colored-border
        color="pink"
        elevation="2"
      >
        <v-row justify="center">
          <v-col
            ><v-img
              src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Flag_of_France.svg"
              height="30"
              width="45"
              title="Français"
            ></v-img
          ></v-col>
          <v-col
            ><v-img
              src="https://upload.wikimedia.org/wikipedia/commons/b/ba/Flag_of_Germany.svg"
              height="30"
              width="45"
              title="Allemand"
            ></v-img
          ></v-col>
          <v-col
            ><v-img
              src="https://upload.wikimedia.org/wikipedia/commons/a/ae/Flag_of_the_United_Kingdom.svg"
              height="30"
              width="45"
              title="Anglais"
            ></v-img
          ></v-col>
        </v-row>
        <v-row justify="center">
          <v-col>Langue maternelle</v-col>
          <v-col>C1/C2<br />(Test-DaF TDN 5)</v-col>
          <v-col>B1/B2</v-col>
        </v-row>
      </v-alert>

      <v-card-title class="text-h4 font-weight-light mb-4 justify-center"
        ><v-icon
          class="mdi mdi-book-multiple-outline mr-10"
          aria-hidden="true"
          color="black"
        ></v-icon
        >Découvrez mon portfolio</v-card-title
      >
      <v-expansion-panels focusable>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Impôts</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="mdWQWvN"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Impôts"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/mdWQWvN"> Impôts</a> by
                Camille (<a href="https://codepen.io/cmathien">@cmathien</a>) on
                <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script>
          </v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Reprographie</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="NWpEjNp"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Reprographie"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/NWpEjNp">
                  Reprographie</a
                >
                by Camille (<a href="https://codepen.io/cmathien">@cmathien</a>)
                on <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Heure</v-expansion-panel-header
          >
          <v-expansion-panel-content
            ><p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="xxqQdOm"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Heure"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/xxqQdOm"> Heure</a> by
                Camille (<a href="https://codepen.io/cmathien">@cmathien</a>) on
                <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script>
          </v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Monnaie à rendre</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="dyvQWOx"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Monnaie à rendre"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/dyvQWOx"> dyvQWOx</a>
                by Camille (<a href="https://codepen.io/cmathien">@cmathien</a>)
                on <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >E-mail</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="xxqQdqB"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="E-mail"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/xxqQdqB"> E-mail</a> by
                Camille (<a href="https://codepen.io/cmathien">@cmathien</a>) on
                <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Prime d'assurance</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="BaWGRdp"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Prime d'assurance"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/BaWGRdp"> BaWGRdp</a>
                by Camille (<a href="https://codepen.io/cmathien">@cmathien</a>)
                on <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Mot de passe</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="ZEemKXj"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Mot de passe"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/ZEemKXj">
                  Mot de passe</a
                >
                by Camille (<a href="https://codepen.io/cmathien">@cmathien</a>)
                on <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Juste Prix</v-expansion-panel-header
          >
          <v-expansion-panel-content>
            <p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="ExWOmez"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Juste Prix"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/ExWOmez">
                  Juste Prix</a
                >
                by Camille (<a href="https://codepen.io/cmathien">@cmathien</a>)
                on <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script
          ></v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header class="text-h6 font-weight-light text-pink"
            >Pendu</v-expansion-panel-header
          >
          <v-expansion-panel-content
            ><p
              class="codepen"
              data-height="500"
              data-theme-id="dark"
              data-default-tab="result"
              data-user="cmathien"
              data-slug-hash="GRWwmLW"
              style="height: 500px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;"
              data-pen-title="Pendu"
            >
              <span
                >See the Pen
                <a href="https://codepen.io/cmathien/pen/GRWwmLW"> Pendu</a> by
                Camille (<a href="https://codepen.io/cmathien">@cmathien</a>) on
                <a href="https://codepen.io">CodePen</a>.</span
              >
            </p>
            <script
              async
              src="https://cpwebassets.codepen.io/assets/embed/ei.js"
            ></script>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-sheet>

    <!--Séparation visuelle-->

    <v-parallax
      src="https://images.pexels.com/photos/2457317/pexels-photo-2457317.png?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
      height="100"
      class="animate__animated animate__fadeIn"
    >
    </v-parallax>

    <!--Informations personnelles et contact-->

    <v-sheet light tile
      ><v-row>
        <v-col>
          <v-card-title class="text-h4 font-weight-light mb-4 justify-center"
            ><v-icon
              class="mdi mdi-card-account-details-outline mr-10"
              aria-hidden="true"
              color="black"
            ></v-icon
            >Informations personnelles</v-card-title
          >
          <v-alert color="cyan" dark icon="mdi-home" border="left" prominent>
            28, rue Rémy Cogghe • 59100 ROUBAIX
          </v-alert>
          <v-alert color="cyan" dark icon="mdi-phone" border="left" prominent>
            06•71•50•24•26
          </v-alert>
          <v-alert color="cyan" dark icon="mdi-at" border="left" prominent>
            camille.mathien@gmail.com
          </v-alert>
          <v-alert color="cyan" dark border="left">
            <a
              href="https://www.linkedin.com/in/camille-mathien/"
              target="_blank"
            >
              <v-img
                :src="require('assets/linkedin.png')"
                aspect-ratio="1"
                max-height="40"
                max-width="40"
                class="rounded-lg ml-2 linkedIn"
                title="Lien vers profil LinkedIn"
              ></v-img>
            </a>
          </v-alert>
        </v-col>
        <v-col>
          <v-card-title class="text-h4 font-weight-light mb-4 justify-center"
            ><v-icon
              class="mdi mdi-mailbox-outline mr-10"
              aria-hidden="true"
              color="black"
            ></v-icon
            >Formulaire de contact</v-card-title
          >
          <div class="text-center">
            <v-col>
              <form>
                <v-text-field
                  v-model="name"
                  :error-messages="nameErrors"
                  :counter="50"
                  label="Nom"
                  required
                  @input="$v.name.$touch()"
                  @blur="$v.name.$touch()"
                ></v-text-field>
                <v-text-field
                  v-model="email"
                  :error-messages="emailErrors"
                  label="E-mail"
                  required
                  @input="$v.email.$touch()"
                  @blur="$v.email.$touch()"
                ></v-text-field>
                <v-divider></v-divider>
                <v-text-field
                  v-model="objet"
                  label="Objet"
                  counter
                  maxlength="40"
                  single-line
                  full-width
                ></v-text-field>
                <v-divider></v-divider>
                <v-textarea
                  v-model="message"
                  label="Message"
                  counter
                  maxlength="500"
                  full-width
                  single-line
                ></v-textarea>
                <v-checkbox
                  v-model="checkbox"
                  :error-messages="checkboxErrors"
                  label="Êtes-vous un humain?"
                  required
                  @change="$v.checkbox.$touch()"
                  @blur="$v.checkbox.$touch()"
                >
                </v-checkbox>
                <v-btn class="mr-4" color="cyan" @click="submit">
                  Valider
                </v-btn>
                <v-btn @click="clear">
                  Réinitialiser
                </v-btn>
              </form>
            </v-col>
          </div>
        </v-col>
      </v-row>
    </v-sheet>

    <!--Séparation visuelle-->

    <v-parallax
      src="https://images.pexels.com/photos/2457317/pexels-photo-2457317.png?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
      height="100"
      class="animate__animated animate__fadeIn"
    >
    </v-parallax>

    <!--Footer-->
    
    <v-footer padless>
      <v-card
        flat
        tile
        class="cyan lighten-1 white--text text-center"
        width="100%"
      >
        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Camille Mathien</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<!--Script-->

<script>
import { validationMixin } from "vuelidate";
import { required, maxLength, email } from "vuelidate/lib/validators";
export default {
  mixins: [validationMixin],

  validations: {
    name: { required, maxLength: maxLength(50) },
    email: { required, email },
    checkbox: {
      checked(val) {
        return val;
      }
    }
  },

  data: () => ({
    sheet: false,
    name: "",
    email: "",
    checkbox: false,
    years: [
      {
        color: "pink",
        year: "2021 (en cours)",
        title: "Développeur web et web mobile",
        text: "AFPA (Roubaix, France)",
        icon: "mdi-school"
      },
      {
        color: "cyan",
        year: "Novembre 2017 – Juillet 2020",
        title: "Traductrice-relectrice",
        text: "Trans4europe (Roubaix, France)",
        icon: "mdi-briefcase"
      },
      {
        color: "cyan",
        year: "Novembre 2015 – Février 2016",
        title: "Stagiaire professeur d’allemand",
        text: "Collège Alphonse Daudet (Nice, France)",
        icon: "mdi-briefcase"
      },
      {
        color: "cyan",
        year: "Mai 2015 – Juillet 2015",
        title: "Stagiaire professeur de français langue étrangère",
        text: "Sankt Marien-Schulen (Ratisbonne, Allemagne)",
        icon: "mdi-briefcase"
      },
      {
        color: "pink",
        year: "2014 – 2016",
        title:
          "Master « Métier de l’enseignement, de l\’éducation et de la formation, second degré, spécialité allemand » • Master « Lehramt International »",
        text:
          "Université Nice Sophia Antipolis (France) • ÉSPÉ de l’Académie de Nice (France) • Universität Regensburg (Allemagne)",
        icon: "mdi-school"
      },
      {
        color: "cyan",
        year: "Octobre 2013 – Mai 2014",
        title: "Assistante de français langue étrangère",
        text: "Hebbelschule (Kiel, Allemagne)",
        icon: "mdi-briefcase"
      },
      {
        color: "pink",
        year: "2010 – 2013",
        title:
          "Licence « Langues, littératures et civilisations étrangères, spécialité allemand »",
        text:
          "Université d’Angers (France) • Bergische Universität Wuppertal (Allemagne) : Erasmus (semestres 5 et 6)",
        icon: "mdi-school"
      },
      {
        color: "pink",
        year: "2010",
        title:
          "Baccalauréat « Économique et social, option européenne Allemand »",
        text: "Lycée La Colinière (Nantes, France)",
        icon: "mdi-school"
      }
    ]
  }),

  computed: {
    checkboxErrors() {
      const errors = [];
      if (!this.$v.checkbox.$dirty) return errors;
      !this.$v.checkbox.checked &&
        errors.push("Vous devez cocher cette case pour continuer !");
      return errors;
    },
    selectErrors() {
      const errors = [];
      if (!this.$v.select.$dirty) return errors;
      !this.$v.select.required && errors.push("Champ obligatoire");
      return errors;
    },
    nameErrors() {
      const errors = [];
      if (!this.$v.name.$dirty) return errors;
      !this.$v.name.maxLength &&
        errors.push("Votre nom ne peut dépasser les 50 caractères");
      !this.$v.name.required && errors.push("Nom obligatoire");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.email && errors.push("E-mail invalide");
      !this.$v.email.required && errors.push("E-mail requis");
      return errors;
    }
  },

  methods: {
    submit() {
      this.$v.$touch();
    },
    clear() {
      this.$v.$reset();
      this.name = "";
      this.email = "";
      this.objet = "";
      this.message = "";
      this.checkbox = false;
    }
  }
};
</script>

<!--Feuille de style-->

<style lang="scss">
.linkedIn:hover {
  box-shadow: 5px 5px 15px whitesmoke;
}

.photo {
  border: solid white 7px;
}
#spin:after {
  content: "";
  animation: spin 3200ms linear infinite;
}
@keyframes spin {
  0% {
    content: "en formation";
  }
  50% {
    content: "à la recherche d'un stage";
  }
  100% {
    content: "motivée !";
  }
}
.v-progress-circular {
  margin: 1rem;
}
</style>
