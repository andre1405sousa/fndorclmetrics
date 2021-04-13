<template>
    <div>
        <table class="table table-striped">
            <caption>Database</caption>
            <thead>
                <tr>
                <th>Nome</th>
                <th>Valor</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="dbInfo of dbInfos" :key="dbInfo.id" class="active">
                <td>{{ dbInfo.chave }}</td>
                <td>{{ dbInfo.chaveValor }}</td>
                </tr>
            </tbody>
        </table>        
    </div>
</template>

<script>
import omdbinfo from "@/services/omdbinfo"

export default {
    data() {
        return {
            dbInfos: []
        }
    },
    mounted() {
        omdbinfo.listar().then(res => {
            this.dbInfos = res.data
        })
    }
}
</script>

<style scoped>
    .table {
        font-size: 10px;
    }
    caption {
        background-color: burlywood;
        font-weight: bold;
    }

</style>