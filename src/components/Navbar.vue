<template>
  <nav>
    <v-navigation-drawer
      v-model="drawer"
      dark
      app
      mini-variant
      class="pink accent-2"
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
  </nav>
</template>
