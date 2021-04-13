<template>
    <div>
        <table class="table table-striped">
        <caption>Active Transactions</caption>
        <thead>
            <tr>
            <th>SID</th>
            <th>Username</th>
            <th>Start Time</th>
            <th>Name</th>
            <th>Used Ublk</th>
            <th>Status</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="activetrans of ats" :key="activetrans.vw_id" class="active">
                <td>{{activetrans.sid}}</td>
                <td>{{activetrans.username}}</td>
                <td>{{activetrans.start_time}}</td>
                <td>{{activetrans.name}}</td>
                <td>{{activetrans.used_ublk}}</td>
                <td>{{activetrans.status}}</td>
            </tr>
        </tbody>
        </table>        
    </div>
</template>

<script>
import activetrans from "@/services/activetrans"

export default {
    data() {
        return {
            ats: []
        }
    },
    mounted() {
        activetrans.listar().then(res => {
            this.ats = res.data
        })
    }
}

</script>

<style scoped>
    .table {
        font-size: 10px;
    }
    caption {
        background-color:darkseagreen;
        font-weight: bold;
    }

</style>