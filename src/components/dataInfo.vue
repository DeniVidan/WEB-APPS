<template>
    <div class="data">
        <div class="card">
            <p>id: {{ id }}</p>
            <p>details: {{ details }}</p>
            <router-link :to="{ name: 'MoreDetails', params: { ID : id } }"> VIŠE </router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: "dataInfo",
    props: {
        id : String,
        details: String,
    }
}
</script>

<style scoped>
*{
    margin: 0;
    padding: 0;
}
.card{
    margin: 0px 20px 10px 20px;
    text-align: start;
    padding: 20px;
    border-radius: 10px;
    border: 1px solid black;
}
.button{
    padding: 20px;
}
</style>
