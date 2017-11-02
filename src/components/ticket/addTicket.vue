<template>
  <div class="layout-padding justify-center content-container">
    <div class="content">
      <div class="header">
        <h4>发布你的票票</h4>
      </div>
      <q-field :count="10">
        <q-input float-label="给你的票票一个标题" v-model="title" />
      </q-field>
      <q-field :count="30">
        <q-input float-label="写上你的赠送箴言" type="textarea" v-model="wishText" :max-height="100" :min-rows="2" />
      </q-field>
      <q-field>
        <q-datetime inverted color="secondary" v-model="sendDate" stack-label="选择派送的时间" />
      </q-field>
    </div>
    <div class="save-btn">
      <q-btn color="light" @click="cancel">再想想</q-btn>
      <q-btn color="secondary" @click="addTicketData">发出</q-btn>
    </div>
  </div>
</template>

<script>
import {QTabs, QTab, QField, QInput, QDatetime, QBtn, Loading} from 'quasar'
import { mapActions } from 'vuex'

export default {
  components: {
    QTabs,
    QTab,
    QField,
    QInput,
    QDatetime,
    QBtn,
    Loading
  },

  data () {
    return {
      title: '',
      wishText: '',
      sendDate: null
    }
  },

  methods: {
    ...mapActions([
      'addTicket'
    ]),
    addTicketData () {
      let ticket = {
        title: this.title,
        wishText: this.wishText,
        sendDate: this.sendDate
      }
      Loading.show()
      this.addTicket(ticket).then((response) => {
        if (response.success) {
          Loading.hide()
          this.resetModel()
          this.$router.push('/')
        }
      })
    },
    cancel () {
      this.resetModel()
      this.$router.push('/')
    },
    resetModel () {
      this.titel = ''
      this.wishText = ''
      this.sendDate = null
    }
  }
}
</script>

<style lang="stylus">
.content-container
  width 690px
  margin 0 auto

  .content
    margin-bottom 100px

  .save-btn
    text-align center
    .q-btn
      width 100px

</style>
