<template>
    <div class="house">
    <img :src="house.imgUrl">
    <h5>Price: {{house.price}}</h5>
    <h5>Year: {{house.year}}</h5>
    <h5>Beds: {{house.bedrooms}}</h5>
    <h5>Bath: {{house.bathrooms}}</h5>
    <h5>Description: {{house.description}}</h5>
    <h5>Levels: {{house.levels}}</h5>
    <button class="btn btn-danger"></button>
    </div>
</template>


<script>
export default {
    name: 'house',
    data(){
        return {};
    },
    mounted(){
        let payload = {
            houseId: this.$route.params.houseId
        };
        this.$store.dispatch('getHouseById', payload);
    },
    computed:{
        house(){
            return this.$store.state.activeHouse;
        }
    },
    methods:{},
    components:{}
}
</script>


<style scoped>
    img{
        height: 300px
    }

</style>