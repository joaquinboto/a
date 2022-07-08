<template>
  <section class="pb-8" id="contact">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row justify="center">
            <v-col cols="12" sm="5">
              <h1 class="font-weight-light display-1">Cartera Demo</h1>
              <h3 class="font-weight-light mt-3">
                Simule su visión antes de actuar.<br>
                Viva el día a dia del mercado y conozca como operar.<br>
                Obtenga informes diarios para saber como rinden los <br>
                distintos instrumentos del mercado.
              </h3>
              <ul>4 comandos para guiar la cartera
                  <li>Rebalancear de acciones.</li>
                  <li>Cambiar el monto invertido.</li>
                  <li>Resetear el perfil de riesgo.</li>
                  <li>Liquidar la cartera.</li>
              </ul>
              <h3 class="font-weight-light mt-3">
                <!-- Telephone: +xx (xx) xxxxx-xxxx -->
              </h3>
              <h3 class="font-weight-light">
                Email: dr.reyeslorenzo@gmail.com
              </h3>
            </v-col>
            <v-col cols="12" sm="7">
              <v-form ref="form" v-model="valid" :lazy-validation="lazy" @submit.prevent="sendEmail">
                <v-text-field
                    v-model="name"
                    type="text"
                    :rules="nameRules"
                    label="Nombre"
                    required
                ></v-text-field>

                <v-text-field
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                ></v-text-field>

                <v-select
                    v-model="market"
                    :rules="marketRules"
                    :items="items"
                    label="Mercado a Operar"
                    required
                ></v-select>
                <v-select
                    v-model="risk"
                    :rules="riskRules"
                    :items="perfil"
                    label="Perfil de Riesgo"
                    required
                ></v-select>
                <v-text-field
                    v-model="money"
                    :rules="moneyRules"
                    label="Monto a Invertir"
                    pattern="^\$\d{1,3}(,\d{3})*(\.\d+)?$"
                    value=""
                    data-type="currency"
                    placeholder="$1,000,000.00"
                    required
                ></v-text-field>                
                <v-btn
                    :disabled="!valid"
                    color="primary"
                    :dark="valid"
                    rounded
                    block
                    class="mt-3"
                    type="submit" value="Send"
                >
                  Enviar
                </v-btn>
              </v-form>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-snackbar
        v-model="snackbar.enabled"
        timeout="3000"
        right
        top
        :color="snackbar.color"
    >
      {{ snackbar.text }}

      <template v-slot:action="{ attrs }">
        <v-btn
            text
            v-bind="attrs"
            @click="snackbar.enabled = false"
        >
          Fechar
        </v-btn>
      </template>
    </v-snackbar>
  </section>
</template>

<style scoped>
#contact {
  background-color: #f4f7f5;
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

</style>

<script>
import emailjs from 'emailjs-com';

export default {
  data: () => ({
    items: ["Argentina","AUSTRALIA","Brasil","Cedears","China","CRYPTO","Japon","UK","USA","CANADA"],
    perfil: ["Cero","Conservador","Mediano","Agresivo"],
    icons: ["fa-facebook", "fa-twitter", "fa-linkedin", "fa-instagram"],
    valid: true,
    name: "",
    nameRules: [
      (v) => !!v || "Nombre Obligatorio",
      (v) => (v && v.length >= 6) || "6 caracteres como mínimo",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "Email obligatorio",
      (v) => /.+@.+\..+/.test(v) || "Mail válido",
    ],
    market: "",
    marketRules: [
      (v) => !!v || "Eliga Mercado a Operar",
    ],
    risk: "",
    riskRules: [
      (v) => !!v || "Especifique perfil de Riesgo",
    ],
    money: "",
    moneyRules: [
      (v) => !!v || "Monto a simular la inversión",
    ],
    lazy: false,
    snackbar: {
      enabled: false,
      text: '',
      color: ''
    }
  }),
  methods: {
    sendEmail(e) {
      /* try { */
        emailjs.sendEmail('service_8wg43f2', 'template_5j26ete', e.target, 'user_RKGACIAAlReOAYqz37clp', {
          name: this.name,
          email: this.email,
          market: this.market,
          risk: this.risk,
          money: this.money,
          })}
          ,/* ).then(() => {
            this.snackbar.text = "Succesffull client subscription"
            this.snackbar.color = "success"
            this.snackbar.enabled = true
          }).catch(() => {
            this.snackbar.text = "Wrong to subscribe"
            this.snackbar.color = "danger"
            this.snackbar.enabled = true
            }); */
          /* } catch(err) {
            console.log({err})
          } */
      /* } */    
  }
};
</script>