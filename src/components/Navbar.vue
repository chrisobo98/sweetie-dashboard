<template>
  <nav>
    <v-navigation-drawer
      v-model="drawer"
      dark
      app
      mini-variant
      class="gray accent-5"
    >
      <v-list tile>
        <v-list-item class="mb-8" router to="/">
          <v-list-item-action>
            <v-icon>fas fa-truck-loading</v-icon>
          </v-list-item-action>
        </v-list-item>
        <v-list-item class="mb-8" router to="/">
          <v-list-item-action>
            <v-icon>fas fa-address-card</v-icon>
          </v-list-item-action>
        </v-list-item>
        <v-list-item class="mb-8" router to="/">
          <v-list-item-action>
            <v-icon>fas fa-tasks</v-icon>
          </v-list-item-action>
        </v-list-item>
        <v-list-item class="mb-8" router to="/">
          <v-list-item-action>
            <v-icon>fas fa-tools</v-icon>
          </v-list-item-action>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-navigation-drawer
      v-model="right"
      dark
      app
      class="gray accent-5"
      fixed
      right
    >
      <v-layout column align-center>
        <v-flex class="mt-5">
          <v-avatar size="200">
            <img src="/facepic.jpeg" alt="a regular sweetie" />
          </v-avatar>
          <h3 class="white--text subheading mt-4 text-center">
            Christopher Bermudez
          </h3>
          <h4 class="white--text subheading mt-1 text-center">Driver</h4>
        </v-flex>
      </v-layout>
      <p class="white--text subheading pl-3 mt-3">Eastern Virginia</p>
      <v-list rounded dense>
        <v-list-item router to="/">
          <v-list-item-action>
            173,760
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>The Miles Driven</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item router to="/">
          <v-list-item-action>
            1576
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Cars Delivered</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item router to="/">
          <v-list-item-action>
            21
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Accrued PTO Days</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <p class="white--text subheading pl-3 mt-3">Pickup Timeline</p>
      <v-timeline align-top dense fill-dot small dark>
        <v-timeline-item fill-dot small color="pink accent-2" class="white--text"
          >Ford of Richland</v-timeline-item
        >
        <v-timeline-item fill-dot small color="pink accent-2" class="white--text"
          >357 Coolway Ave, Richland, Virginia</v-timeline-item
        >
        <v-timeline-item fill-dot small color="pink accent-2" class="white--text"
          >17685 Montrose Street, Roanoke, Virginia</v-timeline-item
        >
                <v-timeline-item fill-dot small color="pink accent-2" class="white--text"
          >32456 Lakeshore Avenue, Roanoke, Virginia</v-timeline-item
        >
        <v-timeline-item fill-dot small color="pink accent-2" class="white--text"
          >HQ</v-timeline-item
        >
      </v-timeline>
    </v-navigation-drawer>
  </nav>
</template>
