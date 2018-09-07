<template>
    <div id='main'>
        <div class='header'>
            <Header />
        </div>
        <div class='horizontal'>
            <div class="add-and-map">
                <div>
                    <AddCountry v-bind:post="locationData2" v-on:onSubmit='onSubmit' v-bind:form="form" />
                </div>
                <div>
                    <MapConfig />
                </div>
            </div>
            <div>
                <Locations v-bind:post="locationData2" v-on:deletePost='deletePost' />
            </div>
        </div>
        <Footer />
    </div>
</template>

<script>
    import Header from "@/components/Header";
    import AddCountry from "@/components/AddCountry";
    import MapConfig from "@/components/MapConfig";
    import Locations from "@/components/Locations";
    import Footer from "@/components/Footer";
    export default {
        name: "Main",
        components: {
            Header,
            AddCountry,
            MapConfig,
            Locations,
            Footer
        },
        data() {
            return {
                locationData2: null,
                locationUrl: "https://travel-bug-backend.herokuapp.com/posts/profile/" +
                    this.$route.query.user,
                postsURL: "https://travel-bug-backend.herokuapp.com/posts",
                form: {
                    profile_id: "",
                    country_name: "",
                    goal_date: "",
                    activities: "",
                    visited: ""
                }
            }
    
        },
        created() {
            this.fetchCountries();
        },
    
        methods: {
            fetchCountries: function() {
                console.log('fetched')
                fetch(this.locationUrl, {
                        method: "get",
                        mode: "cors",
                        headers: new Headers({
                            "Content-Type": "application/json"
                        })
                    })
                    .then(resp => resp.json())
                    .then(resp => {
                        this.locationData2 = resp.posts;
                    })
            },
            deletePost(locationPost) {
                console.log(this.locationData2)
                fetch("https://travel-bug-backend.herokuapp.com/posts/" + locationPost.location_post_id, {
                    method: "DELETE",
                })
                this.locationData2 = this.locationData2.filter((element) => {
                    return element.location_post_id !== locationPost.location_post_id
                })
            },
            onSubmit(form) {
                this.form.profile_id = this.$route.query.user;
                return fetch(this.postsURL, {
                        method: "post",
                        headers: new Headers({
                            "Content-Type": "application/json"
                        }),
                        body: JSON.stringify(this.form)
                    })
                    .then(console.log(this.form))
                    .then(resp => {
                        console.log(resp);
                        if (!resp.ok) {
                            if (resp.status >= 400 || resp.status < 500) {
                                return resp.json().then(data => {
                                    const err = {
                                        errorMessage: data.message
                                    };
                                    throw err;
                                });
                            }
                            const err = {
                                errorMessage: "Blah"
                            };
                            throw err;
                        }
                        this.form.profile_id = ""
                        this.form.country_name = ""
                        this.form.goal_date = ""
                        this.form.activities = ""
                        this.form.visited = ""
                        return resp.json();
                    })
                    .then(this.fetchCountries())
    
            }
        }
    }
</script>

<style>
    body,
    html {
        height: 100vh;
        background-size: 100% auto;
        background-repeat: no-repeat;
        transition: background-image 2s;
        background: fixed;
    }
    
    .horizontal {
        display: flex;
        margin-left: 7vh;
        margin-right: 7vh;
    }
    
    .add-and-map {
        display: flex;
        flex-flow: column;
        justify-items: center;
        align-items: center;
    }
</style>

