<template>
    <div class="main">
        <p id="title" @click="areOptionsVisible = !areOptionsVisible">{{selected}}</p>
        <div class="options" v-if="areOptionsVisible">
            <p v-for="option in options"
               :key="option.value"
               @click="choose(option)">
                {{option.value}}. {{option.name}}
            </p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "vueSelect",
        data() {
            return {
                areOptionsVisible: false,
            }
        },
        mounted() {
            document.addEventListener('click', this.hideSelect.bind(this), true)
        },
        beforeDestroy() {
            document.removeEventListener('click',this.hideSelect)
        },
        methods: {
            choose(option) {
                this.$emit('select', option)
                this.areOptionsVisible = false
            },
            hideSelect() {
                this.areOptionsVisible = false
            }
        },
        props: ['options', 'selected']
    }
</script>

<style scoped>
    .main {
        position: relative;
        width: 200px;
    }


    .main p {
        margin: 0;
        cursor: pointer;
    }

    #title {
        border: 1px solid black;
    }

    .options {
        border: 1px solid black;
        top: 30px;
        right: 0;
        width: 100%;
        position: absolute;

    }

</style>