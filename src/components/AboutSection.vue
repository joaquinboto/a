<template>
  <section id="about">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="7">
              <h1 class="font-weight-light display-2">Quienes somos</h1>
              <h1 class="font-weight-light display-1 mb-3">
                &lt;QUANVAS/&gt;
              </h1>
              <v-row>
                <v-col cols="12" class="d-flex align-center">
                  <v-img
                    src="@/assets/img/calcgear.png"
                    max-width="60px"
                    class="mr-4"
                  />
                  <p class="text-justify">
                    Finanzas 3.0 un espacio que utiliza al máximo
                    todas las herramientas de la programación a fin
                    de tener un diagnóstico completo del mercado y
                    tener un menu  más amplio de oportunidades a invertir.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-img
                    src="@/assets/img/clock.jpeg"
                    max-width="60px"
                    class="mr-4"
                  />
                  <p class="text-justify">
                    Seguimiento en tiempo real de todas las variables tanto
                    situación global como personal. Elaborar asesoramiento 
                    personalizado y estrategias que reflejan la visión del 
                    inversor.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-img
                    src="@/assets/img/icon3.svg"
                    max-width="60px"
                    class="mr-4"
                  />
                  <p class="text-justify">
                    Implementación de trading algorítmico, mediante Bots,
                    carteras ETFs por mercado, sector u industria. Desarrollo de
                    instrumentos que reflejen una visión.
                  </p>
                </v-col>
              </v-row>
            </v-col>
            <v-col cols="12" md="5" class="d-none d-md-flex">
              <v-img
                src="@/assets/img/ill1.svg"
                class="d-block ml-auto mr-auto"
                max-width="400px"
              />
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<style scoped>
#about {
  background-color: #f4f7f5;
}
</style>
