<template>
    <div id="app">
        <vue-select :options="options"
                    @select="optionSelect"
        :selected="selected"></vue-select>

    </div>
</template>

<script>

    import vueSelect from "@/components/vueSelect";

    export default {
        name: 'App',
        data() {
            return {
                selected: 'select',
                options: [
                    {
                        name: 'Espanish', value: 1
                    }, {
                        name: 'Rsuusiasd', value: 2
                    },
                    {
                        name: 'asd', value: 3
                    },
                    {
                        name: 'Espanqwe', value: 4
                    },
                    {
                        name: 'Ezxc', value: 5
                    },
                    {
                        name: 'hghsdfg', value: 6
                    }
                ]
            }
        },
        methods: {
            optionSelect(option) {
                this.selected = option.name
            }
        },
        components: {
            vueSelect
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
