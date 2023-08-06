<template>
    <div>
        <div id="pic">
            <img src="../assets/moh.jpg"/>
        </div>

        <div id="cat-info">
            <div id="field-headers">
                <div>Name: </div>
                <div>Age: </div>


                <div>Neutered: </div>
                <div>Date Caught: </div>
                <div>Date Neutered: </div>
                <div>Date Released: </div>


                <div>
                    <div>Lane: </div>
                </div>

                <div>
                    <div>Phase: </div>
                </div>

                <div>
                    <div>Appearance:</div>
                </div>
            </div>

            <div id="field-values">
                <div>{{ name }}</div>
                <div>{{ age }} Months</div>
 
                <div>
                    <select>
                        <option>
                            Yes
                        </option>

                        <option>
                            No
                        </option>

                        <option>
                            Not Known
                        </option>
                    </select>
                </div>
                
                <div>
                    <input type="date" id="date-caught" value="1/1/2023"/>
                </div>

                <div>
                    <input type="date" id="date-neutered"/>
                </div>


                <div>
                    <input type="date" id="date-released" value="1/1/2023"/>
                </div>

                <div>
                    <select>
                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>Outside APR</option>
                    </select>
                </div>

                <div>
                    <select>
                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>4</option>
                        <option>5</option>
                        <option>6</option>
                        <option>Outside APR</option>
                    </select>
                </div>

                <div>
                    <input type="text" id="description" :value="description"/>
                </div>
            </div>
        </div>

        <button @click=setAppearance()>Abc</button>
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
            },
            description: {
                type: String,
                required: false
            }
        },
        methods: {
            async setAppearance () {
                var response;
                response = await fetch(
                    "http://localhost:8000/cats/1", 
                    {
                        method: "PATCH", 
                        headers: {"accept": "application/json", "Content-Type": "application/json"},
                        body: JSON.stringify(
                            {"appearance": document.getElementById("description").value}
                        )
                    }
                ).then(r => console.log(r.status))
            }
        }
    };
</script>



<style scoped>
    #description {
        height: 50px;
    }

    input {
        text-align: right;
    }
    
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