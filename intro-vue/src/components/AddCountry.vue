<template>
    <div id='country'>
        <form class="country-form">
            <label for='addToList' class="add-to">Add to Your Bucket List!</label>
            <div>
                <input v-model='form.country_name' placeholder=' Country Name' type='text' name='country_name' id='country_name' value=''>
            </div>
            <div>
                <input v-model='form.goal_date' placeholder=' Goal Date' type='text' name='goal_date' id='goal_date' value=''>
            </div>
            <div>
                <textarea v-model='form.activities' placeholder=' Activities you want to do!' type='text' name='activities' id='activities' value=''>Add activities here!</textarea>
            </div>
            <div>
                <input v-model='form.visited' placeholder=' Visited? True or False' type='text' name='visited' id='visited' value=''>
            </div>
            <button @click.prevent="$emit('onSubmit', form)" name='button' class="country-form-button">Add Now!</button>
    
        </form>
    </div>
</template>

<script>
    export default {
        name: "AddCountry",
        data() {
            return {
                locationUrl: "https://travel-bug-backend.herokuapp.com/posts/profile/" + this.$route.query.user,
            }
        },
        props: ['post', 'form'],
    };
</script>

<style>
    .country-form {
        display: flex;
        flex-flow: column;
        flex-wrap: column;
        justify-content: center;
        align-items: center;
        margin-bottom: 5vh;
        background-color: #9fb1bca8;
        border-radius: 15px;
        box-shadow: 8px 8px 8px #444545;
        padding: 1vh;
        width: 24vw;
    }
    
    #country_name,
    #goal_date,
    #activities,
    #visited {
        background-color: white;
        width: 15vw;
        border: 1px solid black;
        margin-bottom: 1vh;
        color: #086788;
        box-shadow: 3px 3px 3px #444545;
        border-radius: 10px;
    }
    
    #activities {
        margin: 0;
    }
    
    textarea:focus,
    input:focus {
        outline: none;
    }
    
    .add-to {
        font-size: 1.2em;
        color: #086788;
        text-shadow: -1px -1px 1px white, 1px 1px 1px white, -1px 1px 1px white, 1px -1px 1px white;
        font-family: "Slackey";
    }
    
    .country-form-button {
        background-color: white;
        color: #086788;
        height: 5vh;
        border-radius: 10px;
        box-shadow: 3px 3px 3px #444545;
        border: 0px;
    }
</style>
