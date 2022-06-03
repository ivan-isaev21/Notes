<template>
    <div class="new-note">
        <label>Title</label>
        <input v-model="note.title" type="text">
        <label>Description</label>
        <textarea v-model="note.descr"></textarea>
        <label>Priority</label>
        <select v-model="note.priority">
            <option value="default">default</option>
            <option value="warning">warning</option>
            <option value="danger">danger</option>
        </select>

        <button class="btn btnPrimary" style="margin-top:2rem;" @click="addNote">New note</button>
    </div>
</template>
<script>
    export default {

        props: {
            note: {
                type: Object,
                required: true
            }
        },
        methods: {
            addNote() {
                this.$emit('addNote', this.note);
            }
        }
    }
</script>
<style lang="scss">
    .new-note {
        text-align: center;
    }
</style>