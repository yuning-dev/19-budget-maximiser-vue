<template>
    <div :class="$style.wrapper">
        <div :class="$style.name">
            {{ item.name }}
        </div>
        <div :class="$style.cost">
            {{ item.cost }}
            <button>Edit</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Item',
    props: {
        item: Object
    }
}
</script>

<style module src="./Item.css"></style>