<template>
  <v-content>
    <section id="hero">
      <v-row no-gutters>
        <v-img
          :min-height="'calc(50vh - ' + $vuetify.application.top + 'px)'"
          src="https://images.unsplash.com/photo-1541746972996-4e0b0f43e02a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
        >
          <v-theme-provider dark>
            <v-container fill-height>
              <v-row
                align="center"
                class="white--text mx-auto"
                justify="center"
              >
                <v-col class="white--text text-center" cols="12" tag="h1">
                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2',
                    ]"
                    class="font-weight-light"
                  >
                    Encuentra tu espacio de trabajo en
                  </span>

                  <br />

                  <span
                    :class="[
                      $vuetify.breakpoint.smAndDown ? 'display-3' : 'display-4',
                    ]"
                    class="font-weight-black"
                  >
                    Coprotel
                  </span>
                </v-col>

                <v-btn
                  class="align-self-end"
                  fab
                  outlined
                  @click="$vuetify.goTo('#about-me')"
                >
                  <v-icon>mdi-chevron-double-down</v-icon>
                </v-btn>
              </v-row>
            </v-container>
          </v-theme-provider>
        </v-img>
      </v-row>
    </section>

    <section id="about-me">
      <div class="py-12"></div>

      <v-container class="text-center">
        <h2 class="display-2 font-weight-bold mb-3">Reserva ya</h2>

        <v-responsive class="mx-auto mb-8" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-responsive
          class="mx-auto title font-weight-light mb-8"
          max-width="720"
        >
          <v-form ref="form" v-model="valid" lazy-validation>
            <p>Selecciona tu ciudad</p>

            <v-overflow-btn
              class="my-2"
              :items="dropdown_icon"
              label="Ciudad"
              target="#dropdown-example"
            ></v-overflow-btn>
          </v-form>
        </v-responsive>

        <div></div>

        <v-btn color="grey" href="/empresas/patito/ubicaciones" outlined large>
          <span class="grey--text text--darken-1 font-weight-bold">
            Reservar Ya
          </span>
        </v-btn>
        <p class="pt-5">
          ¿Rentas espacios? <a href="/empresas/index.vue">Click aquí</a>
        </p>
      </v-container>

      <div class="py-12"></div>
    </section>

    <section id="stats">
      <v-parallax
        :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
        src="https://images.unsplash.com/photo-1483389127117-b6a2102724ae?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60"
      >
        <v-container fill-height>
          <v-row class="mx-auto">
            <v-col
              v-for="[value, title] of features"
              :key="title"
              cols="12"
              md="4"
            >
              <div class="text-center">
                <div
                  class="display-3 font-weight-black mb-4"
                  v-text="value"
                ></div>

                <div
                  class="title font-weight-regular text-uppercase"
                  v-text="title"
                ></div>
              </div>
            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
    </section>
  </v-content>
</template>

<script>
export default {
  name: "home",
  components: {},
  data() {
    return {
      valid: null,
      features: [
        ["Reserva espacios", "+631 disp"],
        ["Registra ubicaciones", "+143 disponibles"],
        ["Aceeso con código QR", "+1532 generados"],
      ],
      dropdown_icon: [
        {
          text: "Ciudad de México",
          callback: () => console.log("Ciudad de México"),
        },
        { text: "Guadalajara", callback: () => console.log("Guadalajara") },
        { text: "Puebla", callback: () => console.log("Puebla") },
      ],
    };
  },
};
</script>
