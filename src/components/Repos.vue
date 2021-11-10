<template>
    <div class="container">
        <div class="content">
            <h2>Projects</h2>
            <div class="flex">
                <Project class="thumbnail" v-for="project in projects" :key="project" v-bind:prj="project"/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Project from '@/components/Project.vue';

@Options({
    components: {
        Project
    },
})

export default class Repos extends Vue {
    private projects: any[] = [];

    mounted(): void { this.fetchProjects() }

    fetchProjects(): void {
        fetch("https://api.github.com/users/esoxy8/repos")
            .then(response => response.json())
            .then(data => {
                for (var prj of data) {
                    var project = {
                        name: prj['name'],
                        description: prj['description'],
                        language: prj['language'],
                        url: prj['html_url']
                };
                this.projects.push(project);
            }
        });
    }
}
</script>


<style scoped lang="scss">
    @import "@/styles/main.scss";

    .container {
        padding: 0 32px 32px 32px;
    }

    .content {
        max-width: 800px;
        padding: 24px;
        margin: auto;
        border-left: 3px solid $turquoise;
        background: $deepGray;
        border-radius: 10px;

        h2 {
            color: $snow;
        }
    }

    .flex {
        display: flex;
        justify-content: flex-start;
        justify-items: flex-start;
        flex-wrap: wrap;
    }
</style>