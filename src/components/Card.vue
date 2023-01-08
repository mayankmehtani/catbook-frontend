<template>
    <div>
        <div id="pic">
            <img src="../assets/moh.jpg"/>
        </div>

        <div id="cat-info">
            <div id="field-headers">
                <div v-if="name">Name: </div>
                <div>Age: </div>


                <div v-if="neuteredStatus">
                    <div>Neutered: </div>
                    <div>Date Caught: </div>
                    <div>Date Neutered: </div>
                    <div>Date Released: </div>
                </div>
                <div>Lane: </div>
                <div>Phase: </div>
            </div>

            <div id="field-values">
                <div>{{ name }}</div>
                <div>{{ age }} months</div>
 
                <div v-if="neuteredStatus">
                    <div>{{ neuteredStatus }}</div>
                    <div>{{ dateCaught }} </div>
                    <div>{{ dateNeutered }} </div>
                    <div>{{ dateReleased }}</div>
                </div>
                <div>{{ Lane }}</div>
                <div>{{ Phase }}</div>
                
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    name: "Card",
    props: {
        name: {
            type: String,
            required: true
        }
    }
};
</script>



<style scoped>
#pic > img {
    height: 370px;
    width: 500px;
}

#cat-info {
    flex-direction: row;
    display: flex;
    justify-content: space-evenly;
}

#field-values {
    text-align: right;
    flex-direction: ;
}
</style>