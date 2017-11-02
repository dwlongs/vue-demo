<template>
  <div>
    <main>
      <!-- <q-gallery-carousel dots infinite autoplay :src="gallery" class="banner">
      </q-gallery-carousel> -->
      <!-- <img src="~assets/quasar-logo-full.svg" alt="banner"> -->
      <ticket-table></ticket-table>
      <!-- <data-table></data-table> -->
      <router-view></router-view>
    </main>
    <q-fab class="fixed add-btn" color="secondary" @click.native="$router.push('/add-ticket')"> 
    </q-fab>
  </div>
</template>

<script>
import {QBtn, QFixedPosition, QFabAction, QGalleryCarousel, QFab} from 'quasar'
import TicketTable from '@/ticket/ticketTable.vue'
// import DataTable from '@/ticket/dataTable.vue'

export default {
  data () {
    return {
      gallery: [
        'statics/banner1.jpg',
        'statics/banner2.jpg'
      ]
    }
  },

  components: {
    QBtn,
    QFixedPosition,
    QGalleryCarousel,
    QFab,
    QFabAction,
    // DataTable,
    TicketTable
  }
}
</script>

<style lang="stylus">
@import '~variables'


.nav-logo
  background-color $green-4

main
  .banner
    height 300px
    .q-carousel-track
      img
        height 300px

.add-btn
  right 40px
  bottom 40px
</style>
