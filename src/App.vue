<template>
  <v-card class="overflow-hidden">
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
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
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
       <v-navigation-drawer
      v-model="drawer"
      absolute
      bottom
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
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
    

    <v-sheet
      id="scrolling-techniques"
      class="overflow-y-auto"
      max-height="1000"
      background-color="pink lighten-4"

    >
      <!-- <v-container style="height: 1000px;"></v-container> -->
    </v-sheet>
    <v-footer
      color="indigo"
      app
    >
      <span class="white--text">&copy; DEEP PATEL 2019</span>
    </v-footer>
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
      items: [
        {
          src: require('C:/Users/deeppatel/cosmic-app/ManchesterUnited.png')           
        },
        {
          src: require('C:/Users/deeppatel/cosmic-app/Liverpool.jpg')
        },
        {
          src: require('C:/Users/deeppatel/cosmic-app/Manchester City.png')
        },
        {
          src: require('C:/Users/deeppatel/cosmic-app/Chelsea.png')
        }
      ]
    }),

    watch: {
      group () {
        this.drawer = false
      },
    },
    }
    </script>

  <!-- script end-->


