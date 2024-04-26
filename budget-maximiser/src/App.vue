<template>
    <div class="wrapper">
        <h1>Budget maximiser</h1>
        <h2>Give us you budget, we'll get you the best value!</h2>
        <div :class="$style.mainWrapper">
            <form :class="[$style.budget, $style.box]" action="javascript:void(0);">
                <div :class="$style.budgetInner">
                    <label for="budget">Your budget</label><input type="text" id="budget">
                </div>
            </form>
            <div :class="[$style.addItemsWrapper, $style.box]">
                <p>Add items</p> <br>
                <form :class="$style.addItemsInnerWrapper" action="javascript:void(0);">
                    <div :class="$style.formItem">
                        <label for="itemName">Item name</label> 
                        <input type="text" id="itemName" v-model="name">
                    </div>
                    <div :class="$style.formItem">
                        <label for="itemCost">Item cost</label> 
                        <input type="text" id="itemCost" v-model="cost">
                    </div>
                </form>
                <div :class="$style.mustHaveWrapper">
                    <label for="mustHave">Is it a must-have</label><input type="checkbox" id="mustHave" @click="toggleMustHave()" >
                </div>
                <button :class="$style.addItemBtn" @click="addItemBtnClicked">Add item</button>
            </div>
            <div :class="$style.itemsList">

            </div>
            <button :class="$style.generateValueBtn">Generate Max Value!</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            name: null,
            cost: null,
            isMustHave: false,
            items: []
        }
    },
    methods: {
        toggleMustHave() {
            if (this.isMustHave) {
                this.isMustHave = false
                console.log('I should be false')
            } else {
                this.isMustHave = true
                console.log('Hi I am true')
            }
        },
        addItemBtnClicked() {
            const item = {
                name: this.name,
                cost: this.cost,
                mustHave: this.isMustHave
            }
            this.items.push(item)
            console.log(item)
            console.log(this.items)
            this.name = ''
            this.cost = ''
        }
    }
}
</script>

<style module src="@/App.css">

</style>
