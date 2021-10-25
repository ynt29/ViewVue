<template>
<div>
    <input type="text" v-model="text">
    <button @click="save()">Save</button>
</div>
</template>

<script>
export default {
    data () {
        return {
            text: null
        }
    },
    methods: {
        save () {
            this.$emit('save', this.text)
        }
    }

}
</script>

<style>

</style>