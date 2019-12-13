<template>
  <v-card class="overflow-hidden">
    <!-- <v-sheet
      id="scrolling-techniques"
      class="overflow-y-auto"
      max-height="3000px"
      background-color="pink lighten-4"
    >-->
    <!--START : App bar -->
    <v-app-bar
      absolute
      color="#fcb69f"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/1920/1080?random"
      scroll-target="#scrolling-techniques"
    >
      <template v-slot:img="{ props }">
        <v-img v-bind="props" gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"></v-img>
      </template>

      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Cosmic Design & Print</v-toolbar-title>
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-email-send</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
    <!--END : App bar -->
    <!-- <v-container style="height: 1000px;"></v-container> -->
    <!--START : Navigation drawer code -->
    <v-navigation-drawer v-model="drawer" absolute bottom temporary>
      <v-list nav dense>
        <v-list-item-group v-model="group" active-class="deep-purple--text text--accent-4">
          <v-list-item>
            <v-list-item-title>Home</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Products</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-title>Email Us</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Contact Info</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <!--END: Navigation drawer code  -->

    <!--Start: Image Slider  -->
    <v-carousel>
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      ></v-carousel-item>
    </v-carousel>
    <!--END: Image Slider  -->

    <!--START: Cards with description  -->

    <!-- 
       <v-container
      v-for="align in alignments"
      :key="align"
      class="grey lighten-5 mb-6"
    >
      <v-row
        :align="align"
        no-gutters
        style="height: 150px;"
      >
        <v-col
          v-for="n in 3"
          :key="n"
        >
         start : card for descrip


        end : card for descrip


      </v-col>
      </v-row>
    </v-container>-->
    <!-- first  -->
    <v-card class="mx-auto" height="absolute" width="50%">
      <v-img
        :src="require('C:/Users/deeppatel/cosmic-app/src/assets/Chelsea.png')"
        height="300px"
        width="300px"
      ></v-img>

      <v-card-title>Manchester United</v-card-title>
      <v-spacer></v-spacer>
      <v-card-actions>
        <!-- <v-btn text>Share</v-btn> 
              <v-btn
                color="purple"
                text
              >
                      Explore
        </v-btn>-->
        <v-btn icon @click="show = !show">
          <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
        </v-btn>
      </v-card-actions>
      <v-card-subtitle>Glory Glory Manchester United</v-card-subtitle>
      <v-expand-transition>
        <div v-show="show">
          <v-divider></v-divider>

          <v-card-text>Manchester United Football Club is a professional football club based in Old Trafford, Greater Manchester, England, that competes in the Premier League, the top flight of English football.</v-card-text>
        </div>
      </v-expand-transition>
    </v-card>
    <!-- first -->
    <!-- second> -->
    <v-card class="mx-auto" height="absolute" width="50%">
      <v-img
        :src="require('C:/Users/deeppatel/cosmic-app/src/assets/Liverpool.jpg')"
        height="300px"
        width="300px"
      ></v-img>

      <v-card-title>Liverpool</v-card-title>
      <v-spacer></v-spacer>
      <v-card-actions>
        <!-- <v-btn text>Share</v-btn> 
              <v-btn
                color="purple"
                text
              >
                      Explore
        </v-btn>-->
        <v-btn icon @click="show = !show">
          <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
        </v-btn>
      </v-card-actions>
      <v-card-subtitle>LIVERPOOL FC LEGENDS V BARÇA LEGENDS</v-card-subtitle>
      <v-expand-transition>
        <div v-show="show">
          <v-divider></v-divider>

          <v-card-text>
            The Club’s official charity, Liverpool FC Foundation, stages its fourth official legends charity game at Anfield.
            The Liverpool FC Legends will take on the greats from Spanish giants Barça Legends in a clash between the European history makers, in aid of the LFC Foundation.
            An array of star players are already confirmed for the Reds line up, including for the first time back playing at Anfield; Fernando Torres, Jose Enrique, and Fabio Aurelio. Luis Garcia, Patrik Berger, Jerzy Dudek, Jason McAteer and Vladimir Smicer are also confirmed to return to the Legends squad.
            Barça Legends side will also feature some fantastic footballing stars, including Patrick Kluivert, Juliano Belletti and Javier Saviola.
          </v-card-text>
        </div>
      </v-expand-transition>
    </v-card>

    <!-- second -->
    <!--END: Cards with description  -->

    <!-- <v-container style="height: 2000px;"></v-container> -->

    <v-footer color="indigo" app>
      <span class="white--text">&copy; DEEP PATEL 2019</span>
    </v-footer>
    <!-- </v-sheet> -->
  </v-card>
</template>

<style>
/* This is for documentation purposes and will not be needed in your application */
#lateral .v-btn--example {
  bottom: 0;
  position: absolute;
  margin: 0px 0px 16px 16px;
}
</style>


  <!--script start -->

    <script>
export default {
  data: () => ({
    drawer: false,
    group: null,
    show: false,
    items: [
      {
        src: require("C:/Users/deeppatel/cosmic-app/src/assets/1.png")
      },
      {
        src: require("C:/Users/deeppatel/cosmic-app/src/assets/2.png")
      },
      {
        src: require("C:/Users/deeppatel/cosmic-app/src/assets/3.png")
      },
      {
        src: require("C:/Users/deeppatel/cosmic-app/src/assets/4.png")
      }
    ]
  }),

  watch: {
    group() {
      this.drawer = false;
    }
  }
};
</script>

  <!-- script end-->


