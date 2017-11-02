<template>
  <div class="layout-padding ticket-table">
    <q-data-table
      :data="tickets"
      :config="config"
      :columns="columns"
    >
    </q-data-table>
  </div>
</template>

<script>
import {
  QDataTable,
  QField,
  QInput,
  QCheckbox,
  QSelect,
  QSlider,
  QBtn,
  QIcon,
  QTooltip,
  QCollapsible
} from 'quasar'

import { mapGetters } from 'vuex'

export default {
  components: {
    QDataTable,
    QField,
    QInput,
    QCheckbox,
    QSelect,
    QSlider,
    QBtn,
    QIcon,
    QTooltip,
    QCollapsible
  },

  mounted () {
    console.log('tickets', this.tickets)
  },

  data () {
    return {
      config: {
        title: 'Data Table',
        refresh: true,
        noHeader: false,
        columnPicker: true,
        leftStickyColumns: 0,
        rightStickyColumns: 2,
        bodyStyle: {
          maxHeight: '500px'
        },
        rowHeight: '50px',
        responsive: true,
        pagination: {
          rowsPerPage: 15,
          options: [5, 10, 15, 30, 50, 500]
        },
        selection: 'multiple'
      },
      columns: [
        {
          label: '标题',
          field: 'title',
          width: '100px'
        },
        {
          label: '祝福',
          field: 'wishText',
          width: '600px'
        },
        {
          label: '发送日期',
          field: 'sendDate',
          width: '100px',
          format (value) {
            return new Date(value).toLocaleString()
          }
        }
      ],
      pagination: true,
      rowHeight: 50,
      bodyHeightProp: 'maxHeight',
      bodyHeight: 500
    }
  },

  computed: {
    ...mapGetters(['tickets'])
  }
}
</script>

<style lang="stylus">
.ticket-table
  table > thead > tr > th
    height 60px
</style>
