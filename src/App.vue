<template>
  <v-app>
    <!--First Toolbar-->
    <v-toolbar class="orange lighten-4" style="height: 8%">

      <v-toolbar-side-icon @click.native.stop="sideNav = !sideNav" class="hidden-lg-and-up"></v-toolbar-side-icon>

      <v-avatar style="margin: 30px 10px 24px 20px">
        <img src="@/assets/logo.png" alt="Fly Mashriq" class="mb-2">
      </v-avatar>

      <v-toolbar-title>Fly Mashriq</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon class="hidden-xs-only hidden-sm-only">
        <v-icon>search</v-icon>
      </v-btn>

      <div>
        <v-btn dark >Log In</v-btn>
      </div>

    </v-toolbar>

    <!--Second Toolbar-->

      <v-toolbar-items style="height: 5%" class="hidden-xs-only hidden-sm-only" >

        <v-list-tile v-for="item in menuItems" :key="item.title" style="list-style: none">

          <v-list-tile-action>
            <v-icon>{{ item.icons }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>{{ item.title }}</v-list-tile-content>
        </v-list-tile>

      </v-toolbar-items>

    <!--Side Navigation open in small devices-->

    <v-navigation-drawer  fixed v-model="sideNav">
      <v-list>
        <v-avatar style="margin: 30px 10px 24px 20px">
          <img src="@/assets/logo.png" alt="Fly Mashriq" class="mb-2">
        </v-avatar>
          Fly Mashriq

        <v-list-tile v-for="item in menuItems" :key="item.title" style="list-style: none">

          <v-list-tile-action>
            <v-icon>{{ item.icons }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>{{ item.title }}</v-list-tile-content>

        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <router-view></router-view>

    <v-footer color="orange lighten-1">
      <span class="white--text">&copy; 2018</span>
    </v-footer>

  </v-app>



</template>

<script>
export default{
  data () {
    return {
      sideNav: false,
      menuItems: [
        {icons: 'supervisor_account', title: 'Air Operator'},
        {icons: 'room', title: 'Aircraft'},
        {icons: 'person', title: 'Empty Legs'},
        {icons: 'face', title: 'Fixed Price'},
        {icons: 'lock_open', title: 'Quote Request'}
      ]
    }
  }
}
</script>
