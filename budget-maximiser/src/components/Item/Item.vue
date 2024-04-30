<template>
    <div :class="$style.wrapper">
        <div :class="$style.name">
            {{ item.name }}
            <!-- <font-awesome-icon icon="fa-solid fa-asterisk" /> -->
        </div>
        <div :class="$style.cost">
            {{ item.cost }}
            <button :class="$style.editBtn" @click="editBtnClicked()">Edit</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Item',
    props: {
        item: Object
    },
    methods: {
        editBtnClicked() {

        }
    }
}
</script>

<style module src="./Item.css"></style>