<template>
  <!-- Configure "view" prop for QLayout -->
  <q-layout>
      <!-- opens drawer below
      <button class="hide-on-drawer-visible" @click="$refs.drawer.open()">
        <i>menu</i>
      </button>
      -->
    <header slot="header">
      <q-tabs class="shadow-2" align="center" color="secondary" v-model="selectedTab">
        <q-tab slot="title" label="票来了" class="nav-logo" @select="select"></q-tab>
        <q-tab slot="title" name="index-tab" label="首页" @click="$router.push('/')" />
        <q-tab slot="title" name="send-tab" label="发出的" @click="$router.push('/')" />
        <q-tab slot="title" name="take-tab" label="收到的" @click="$router.push('/')" />
      </q-tabs>
    </header>

    <!-- Navigation Tabs
    <q-tabs slot="navigation">
      <q-route-tab slot="title" icon="view_quilt" to="/layout/about" replace hide="icon" label="About" />
      <q-route-tab slot="title" icon="view_day" to="/layout/toolbar" replace hide="icon" label="Toolbar" />
      <q-route-tab slot="title" icon="view_day" to="/layout/tabs" replace label="Tabs" />
      <q-route-tab slot="title" icon="input" to="/layout/drawer" replace label="Drawer" />
    </q-tabs>
    -->

    <!-- Left Side Panel
    <div slot="left">
      <q-list no-border link inset-delimiter>
        <q-list-header>Essential Links</q-list-header>
        <q-item>
          <q-item-side icon="school" />
          <q-item-main label="Docs" sublabel="quasar-framework.org" />
        </q-item>
        <q-item>
          <q-item-side icon="record_voice_over" />
          <q-item-main label="Forum" sublabel="forum.quasar-framework.org" />
        </q-item>
        <q-item>
          <q-item-side icon="chat" />
          <q-item-main label="Gitter Channel" sublabel="Quasar Lobby" />
        </q-item>
        <q-item>
          <q-item-side icon="rss feed" />
          <q-item-main label="Twitter" sublabel="@quasarframework" />
        </q-item>
      </q-list>
    </div>
    -->

    <!-- Right Side Panel
    <div slot="right">
      ...
    </div>
    -->

    <router-view />

    <!-- Footer
    <q-toolbar slot="footer">
      ...
    </q-toolbar>
    -->
  </q-layout>
</template>

<script>
import {QLayout, QTabs, QTab} from 'quasar'

export default {
  components: {
    QLayout,
    QTabs,
    QTab
  },

  data () {
    return {
      selectedTab: 'index-tab'
    }
  },

  methods: {
    select () {
      this.selectedTab = 'index-tab'
    }
  }
}
</script>

<style lang="stylus">
.nav-logo
  background-color $green-4
</style>
