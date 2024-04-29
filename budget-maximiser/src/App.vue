<template>
    <div class="wrapper">
        <h1>Budget maximiser</h1>
        <h2>Give us you budget, we'll get you the best value!</h2>
        <div :class="$style.mainWrapper">
            <div>
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
                    <template v-if="this.addBtnClicked && !validName">
                        <div :class="$style.errorDiv">
                            Please enter a valid name.
                        </div>
                    </template>
                    <template v-if="this.addBtnClicked && !validCost">
                        <div :class="$style.errorDiv">
                            Please enter a cost that is > 0.
                        </div>
                    </template>
                    <div :class="$style.mustHaveWrapper">
                        <label for="mustHave">Is it a must-have</label><input type="checkbox" id="mustHave" :checked="isMustHave" @click="toggleMustHave()" >
                    </div>
                    <div :class="$style.addBtnWrapper">
                        <button :class="$style.addItemBtn" @click="addItemBtnClicked">Add item</button>
                    </div>
                </div>
            </div>
            <div :class="$style.itemsList">
                <template v-for="item in items">
                </template>
            </div>
            <!-- <button :class="$style.generateValueBtn">Generate Max Value!</button> -->
        </div>
    </div>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            name: '',
            cost: '',
            isMustHave: false,
            items: [],
            addBtnClicked: false
        }
    },
    computed: {
        validName() {
            const trimmedName = this.name.trim()
            const isNumber = Number(trimmedName)
            if (trimmedName.length > 0 && Number.isNaN(isNumber)) {
                return true
            }
            return false
        },
        validCost() {
            if (!Number.isNaN(this.cost) && this.cost > 0) {
                return true
            }
            return false
        },
    },
    methods: {
        toggleMustHave() {
            this.isMustHave = !this.isMustHave
        },
        addItemBtnClicked() {
            this.addBtnClicked = true
            if (this.validName && this.validCost) {
                const item = {
                    name: this.name,
                    cost: this.cost,
                    mustHave: this.isMustHave
                }

                this.items.push(item)
                this.name = ''
                this.cost = ''
                this.isMustHave = false
                console.log(item)
                console.log(this.items)
            }

        }
    }
}
</script>

<style module src="@/App.css">

</style>
