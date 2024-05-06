<script>
import axios from 'axios';
import ProjectCards from '../components/ProjectCards.vue';

export default {
    name: 'SingleProject',

    components:  {
      ProjectCards
    },

    data() {
        return {
            project: null,
            projectSlug: null,

            apiBaseUrl: 'http://127.0.0.1:8000/api',
        }
    },
    mounted() {

        this.projectSlug = this.$route.params.slug;
        axios.get(this.apiBaseUrl + '/projects/' + this.projectSlug).then(res => {
            if(res.data.success) {
                
                this.project = res.data.project
            } else {

                this.$router.push({name: 'error404'})
            }
        })
    },
}
</script>

<template>

    <div v-if="project">
        <ProjectCards :project="project"></ProjectCards>
    </div>
    <div v-else>
        <div class="spinner-border" role="status">
            <span class="visually-hidden">Loading...</span>
        </div>
    </div>

</template>


<style lang="scss" scoped>
</style>