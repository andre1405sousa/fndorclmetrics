<template>
    <div>
        <table class="table table-striped">
        <caption>Data Files</caption>            
        <thead>
            <tr>
            <th>File Name</th>
            <th>Allocated MB</th>
            <th>Used MB</th>
            <th>Free Space MB</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="dfile of dfiles" :key="dfile.vw_id" class="active">
                <td>{{dfile.file_name}}</td>
                <td class="text-right">{{dfile.allocated_mb}}</td>
                <td class="text-right">{{dfile.used_mb}}</td>
                <td class="text-right">{{dfile.free_space_mb}}</td>
            </tr>
        </tbody>
        </table>        
    </div>
</template>

<script>
import datafilesutilzomdbinfo from "@/services/datafilesutilz"

export default {
    data() {
        return {
            dfiles: []
        }
    },
    mounted() {
        datafilesutilzomdbinfo.listar().then(res => {
            this.dfiles = res.data
        })
    }
}
</script>

<style scoped>
    .table {
        font-size: 10px;
    }
    caption {
        background-color: cornflowerblue;
        font-weight: bold;
    }
</style>