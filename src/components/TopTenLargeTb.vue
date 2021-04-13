<template>
    <div>
        <table class="table table-striped">
        <caption>Top Ten Largest Tables</caption>            
        <thead>
            <tr>
                <th>Segment Name</th>
                <th>Segment Type</th>
                <th>MB</th>
                <th>GB</th>
                <th>Tablespace</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="topten of toptens" :key="topten.vw_id" class="active">
                <td>{{ topten.segment_name }}</td>
                <td>{{ topten.segment_type }}</td>
                <td>{{ topten.mb }}</td>
                <td>{{ topten.gb }}</td>
                <td>{{ topten.tablespace_name }}</td>
            </tr>
        </tbody>
        </table>        
    </div>
</template>

<script>
import toptenlargetb from "@/services/toptenlargetb"

export default {
    data() {
        return {
            toptens: []
        }
    },
    mounted() {
        toptenlargetb.listar().then(res => {
            this.toptens = res.data
        })
    }
}

</script>

<style scoped>
    .table {
        font-size: 10px;
    }
    caption {
        background-color: antiquewhite;
        font-weight: bold;
    }

</style>