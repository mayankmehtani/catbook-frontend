<template>
    <div>
        <div id="pic">
            <img src="../assets/moh.jpg"/>
        </div>

        <div id="cat-info">
            <div id="field-headers">
                <div>Name: </div>
                <div>Age: </div>


                <div v-if="neuteredStatus">
                    <div>Neutered: </div>
                    <div>Date Caught: </div>
                    <div>Date Neutered: </div>
                    <div>Date Released: </div>
                </div>

                <div v-if="lane">
                    <div>Lane: </div>
                </div>

                <div v-if="phase">
                    <div>Phase: </div>
                </div>

                <div v-if="appearance">
                    <div>Appearance</div>
                </div>
            </div>

            <div id="field-values">
                <div>{{ name }}</div>
                <div>{{ age }} Months</div>
 
                <div v-if="neuteredStatus">
                    <div>{{ neuteredStatus }}</div>
                
                    <div v-if="dateCaught">
                        <div>{{ dateCaught }} </div>
                    </div>
                    <div v-else>
                        <div>Not Known</div>
                    </div>

                    <div v-if="dateNeutered">
                        <div>{{ dateNeutered }} </div>
                    </div>
                    <div v-else>
                        <div>Not Known</div>
                    </div>

                    <div v-if="dateReleased">
                        <div>{{ dateReleased }}</div>
                    </div>
                    <div v-else>
                        <div>Not Known</div>
                    </div>

                    <div v-if="lane">
                        <div>{{ lane }}</div>
                    </div>

                    <div v-if="phase">
                        <div>{{ phase }}</div>
                    </div>
                </div>

                <div v-if="appearance">
                    <div>{{ appearance }}</div>
                </div>
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
        },
        age: {
            type: Number,
            required: false
        },
        neuteredStatus: {
            type: String,
            required: false
        },
        dateCaught: {
            type: Date,
            required: false
        },
        dateNeutered: {
            type: Date,
            required: false
        },
        dateReleased: {
            type: Date,
            required: false
        },
        lane: {
            type: Number,
            required: false
        },
        phase: {
            type: Number,
            required: false
        },
        villa: {
            type: Number,
            required: false
        },
        appearance: {
            type: String,
            required: false
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
    }
</style>