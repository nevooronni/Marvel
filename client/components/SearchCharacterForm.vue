<template>
    <div class="search-character__form">
       <a href="" class="icon-marvel-logo-svg" title="home" alt="home" id="character">MARVEL CHARACTER SEARCH</a> 
        <form @submit.prevent
            @submit="handleSearch()" id="form">

            <div class="ui action input">
                <input v-model="name" placeholder="character Name" type="text" required />

                <button class="ui icon pink button">
                    <i class="search icon"></i>
                </button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                name: ''
            }
        },
        methods: {
            handleSearch () {
                this.$store.dispatch('FETCH_CHARACTERS', this.name)
            }
        }
    }
</script>

<style>
    .search-character__form {
        padding-top: 100px;
    }

    #character {
        margin-bottom: 30px;
        color:grey;
        font-weight: bold;
    }

    #form {
        margin-top: 30px;
    }


</style>

