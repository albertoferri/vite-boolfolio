<script>

import {store} from '../store.js';

export default {
    name: 'AppHeader',
    data() {
        return {
            store,
        };
    },
    methods: {
        filterProjects() {
            this.$emit('filter-projects', this.filterQuery);
        },

        applyFilter(filterQuery) {

            if (store.filterQuery.trim() === '') {
                store.filteredProjects = store.projects;
            } else {
                store.filteredProjects = store.projects.filter(project =>
                    project.title.toLowerCase().includes(store.filterQuery.toLowerCase())
                );
                console.log("sono nell'else")
            }
            console.log(store.filterQuery)
        }
    }
}
</script>


<template>

    <header class="bg-body-tertiary">
        <div class="container">
            <nav class="navbar">
                <div class="container-fluid d-flex justify-content-between">

                    <a href="#">
                        <router-link :to="{ name: 'home' }"><img src="https://fontmeme.com/permalink/240430/990fbe74ade8eac19477253ccd13ab23.png" alt="casper-font" border="0"></router-link>
                    </a>

                    <div>
                        <router-link :to="{ name: 'contact-me' }" class="btn btn-outline-info btn-outline">Contattateci</router-link>
                    </div>

                    <div>
                        <input class="form-control" type="search" v-model="store.filterQuery" placeholder="Filtra progetti..." @keyup="applyFilter(store.filterQuery)">
                    </div>

                </div>
            </nav>
        </div>
    </header>

</template>

<style lang="scss">
    
</style>