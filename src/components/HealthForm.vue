<template>
<v-container class="d-flex flex-row align-center text-center">
        <v-container id="section-calories" class="d-flex flex-column align-center text-center" fluid>
            <h3 class="text-h2 my-8 text-primary alkatra">COMPTEUR DE CALORIES</h3>
            <p class="text-h5 my-8 px-12 alkatra">Lorsque l’on souhaite perdre de la graisse ou construire du muscle, la première
                étape
                consiste à évaluer notre dépense énergétique, c'est-à-dire la quantité d’énergie que dépense notre corps au
                cours de la journée. Celle-ci dépend de notre âge, notre poids, notre sexe et bien évidemment de notre
                niveau
                d’activité physique.

                Renseignez le formulaire ci-dessous pour connaître votre dépense énergétique, nous vous expliquerons ensuite
                comment utiliser cette information.
            </p>
        </v-container>

        <v-container class=" d-flex flex-column align-center ">
            <v-form class="form mt-8">
                <v-select color="primary" v-model="genre" ref="genre" label="Sexe" item-title="title" item-value="value"
                    :items="[
                        { value: 'male', title: 'Homme' },
                        { value: 'female', title: 'Femme' }]" variant="underlined" required></v-select>

                <v-text-field color="primary" v-model="age" label="Age :" ref="age" variant="underlined" :rules="inputRules"
                    type="number" required></v-text-field>
                <v-text-field color="primary" v-model="taille" ref="taille" label="Poids :" variant="underlined"
                    :rules="inputRules" type="number" required></v-text-field>
                <v-text-field color="primary" v-model="poids" ref="poids" label="Taille :" variant="underlined"
                    :rules="inputRules" type="number" required></v-text-field>

                <v-select color="primary" v-model="coeff" ref="coeff" label="Activité" item-title="title" item-value="value"
                    :items="[
                        { value: 1, title: 'Journée passée au repos allongé' },
                        { value: 1.2, title: 'Travail sédentaire assis, pas de sport, moins de 30 min de marche' },
                        { value: 1.4, title: 'Travail sédentaire avec 30 min de marche' },
                        { value: 1.6, title: 'Travail sédentaire et 1 h à 1 h 15 de sport' },
                        { value: 1.7, title: 'Travail sédentaire et 1 h 30 à 2 h de sport' },
                        { value: 1.8, title: 'Travail physique avec beaucoup de déplacements et 1 h 30 à 2 h de sport' },
                        { value: 2, title: 'Travail physique et 3 à 4 h de sport' }
                    ]" variant="underlined" required>
                </v-select>

                <v-select color="primary" v-model="metabolisme" label="Métabolisme" item-title="title" item-value="value"
                    :items="[
                        { value: 'fast', title: 'Métabolisme qui brûle rapidement (plutôt maigre et sec)' },
                        { value: 'slow', title: 'Métabolisme plus lent (prise de poids plus facile)' }
                    ]" variant="underlined"></v-select>

                <v-btn @click="handleSubmit(); handleChange()" color="primary">
                    Calculer
                </v-btn>

                <h2 class="mt-6 text-h4 alkatra" v-if="submitted"><span class="text-h3 alkatra">{{ result }} !</span> C’est le nombre de calories que brûle votre corps
                    quotidiennement. Si vous souhaitez perdre de la graisse il vous faudra en consommer un petit peu moins,
                    et
                    si vous souhaitez vous muscler il vous faudra en consommer un peu plus.

                    Un processus simple à comprendre mais compliqué à mettre en œuvre dans la vie de tous les jours.
                    Contactez-nous ici (lien vers la page contact) pour que l’on vous accompagne.
                </h2>

            </v-form>
        </v-container>
    </v-container>
  
</template>

<script>

export default {

  data() {
    return {
      genre: null,
      age: "",
      poids: "",
      taille: "",
      result: null,
      coeff: 1,
      metabolisme: null,
      submitted: false,

      inputRules: [
        v=> v.length >= 2 || 'Informations manquantes'
      ]
    };
  },
    methods: {
        handleSubmit() {
            console.log(this.genre)
            console.log(this.coeff)
            console.log(this.age)
            console.log(this.poids)
            console.log(this.taille)
            if (this.$refs.age.validate() && 
            this.$refs.taille.validate() &&
            this.$refs.poids.validate()){
                if (this.genre == "female") {
                    this.result = Math.round(665.1 + (9.56 * this.poids) + (1.85 * this.taille) - (4.67 * this.age) * this.coeff)
                } else if (this.genre == "male") {
                    this.result = Math.round(66.5 + (13.75 * this.poids) + (5 * this.taille) - (6.77 * this.age) * this.coeff)
                }
                console.log(this.result)
                if (this.result != null) {
                    this.submitted = true
                }
            }
        },
        handleChange() {
            if (this.metabolisme == 'fast') {
                this.result = this.result + (0.1 * this.result)
            } else if (this.metabolisme == 'slow') {
                this.result = this.result - (0.1 * this.result)
            }
        }
    }
};
</script>

<style>
.alkatra{
    font-family: 'Alkatra', cursive !important;
}
.form{
    width: 80%;
}
.textForm{
    width: 90%;
}
</style>