<template>
    <div class="container">
        <div class="columns">
            <div class="column col-6">
                <dbinfo />
            </div>
            <div class="column col-6">
                <toptenlargetb />                
                <hr>
                <activetransaction />                
            </div>
        </div>
        <hr>
        <div class="columns">
            <div class="column col-6">
                <datafileutilz />
            </div>
            <div class="column col-6">
                <memoryused />                
            </div>
        </div>        
    </div>
</template>

<script>
import DbInfo from "@/components/DbInfo"
import MemoryUsed from "@/components/MemoryUsed"
import ActiveTransaction from "@/components/ActiveTransaction"
import DataFileUtilz from "@/components/DataFileUtilz"
import TopTenLargeTb from "@/components/TopTenLargeTb"

export default {
    name: 'App',
    components: { 
        dbinfo: DbInfo,
        memoryused: MemoryUsed,
        activetransaction: ActiveTransaction,
        datafileutilz: DataFileUtilz,
        toptenlargetb: TopTenLargeTb
    }    
}
</script>


<style scoped>

</style>