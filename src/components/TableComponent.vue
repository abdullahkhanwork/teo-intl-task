<template>
    <q-table :rows="tableData" :columns="columns" row-key="id" full-width full-height />
</template>
  
<script>
import { ref } from 'vue'
import axios from 'axios'

export default {
    name: 'TableComponent',
    setup() {
        const tableData = ref([])
        const columns = [
            {
                name: 'id',
                required: true,
                label: 'Id',
                align: 'left',
                field: 'id'
            },
            {
                name: 'name',
                required: true,
                label: 'Name',
                align: 'left',
                field: 'name'
            },
            {
                name: 'rank',
                required: true,
                label: 'Rank',
                align: 'left',
                field: 'rank'
            }
        ]

        axios.get('/dummy.json')
            .then(response => (tableData.value = response.data))

        return { tableData, columns }
    }
}
</script>