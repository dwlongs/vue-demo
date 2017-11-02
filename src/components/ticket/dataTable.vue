<template>
  <div class="layout-padding">
    <q-data-table
      :data="table"
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

const table = [
  {
    'source': 'Audit',
    'severity': 'I',
    'serviceable': 'Informational',
    'callhome': 'N',
    'isodate': '2015-05-19T08:11:05',
    'system_name': 'SN#Y014BG2790EV',
    'event_id': '0000007A',
    'log_number': '4006DC55',
    'message': 'Login successful. User ID userid from Web at IP address 10.72.97.94.',
    'event_number': '4001A5AD',
    'cmm_event_id': '',
    'unique_id': 1,
    'timerange': 2
  },
  {
    'source': 'Audit',
    'severity': 'I',
    'serviceable': 'Informational',
    'callhome': 'N',
    'isodate': '2015-05-19T08:11:05',
    'system_name': 'SN#Y014BG2790EV',
    'event_id': '0000007A',
    'log_number': '4006DC55',
    'message': 'Login successful. User ID userid from Web at IP address 10.72.97.94.',
    'event_number': '4001A5AD',
    'cmm_event_id': '',
    'unique_id': 1,
    'timerange': 2
  },
  {
    'source': 'Audit',
    'severity': 'I',
    'serviceable': 'Informational',
    'callhome': 'N',
    'isodate': '2015-05-19T08:11:05',
    'system_name': 'SN#Y014BG2790EV',
    'event_id': '0000007A',
    'log_number': '4006DC55',
    'message': 'Login successful. User ID userid from Web at IP address 10.72.97.94.',
    'event_number': '4001A5AD',
    'cmm_event_id': '',
    'unique_id': 1,
    'timerange': 2
  }
]

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

  data () {
    return {
      table,
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
          label: 'Date',
          field: 'isodate',
          width: '140px'
        },
        {
          label: 'Service',
          field: 'serviceable',
          width: '70px'
        }
      ],

      pagination: true,
      rowHeight: 50,
      bodyHeightProp: 'maxHeight',
      bodyHeight: 500
    }
  }
}
</script>

<style lang="stylus">
</style>
