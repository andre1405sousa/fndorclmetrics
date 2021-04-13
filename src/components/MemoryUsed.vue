<template>
    <div>
        <table class="table table-striped">
        <caption>SGA and PGA Status</caption>
        <thead>
            <tr>
            <th>Nome</th>
            <th>Valor</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="mu of memoryuseds" :key="mu.vw_id" class="active">
            <td>{{ mu.nm }}</td>
            <td class="text-right">{{ mu.mb }} MB</td>
            </tr>
        </tbody>
        </table>        
    </div>
</template>

<script>
import memoryused from "@/services/memoryused"

export default {
    data() {
        return {
            memoryuseds: []
        }
    },
    mounted() {
        memoryused.listar().then(res => {
            this.memoryuseds = res.data
        })
    }
}
</script>

<style scoped>
    .table {
        font-size: 10px;
    }
    caption {
        background-color: bisque;
        font-weight: bold;
    }

</style>