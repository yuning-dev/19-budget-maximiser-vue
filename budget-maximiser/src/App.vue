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
                        <input type="text" id="itemName">
                    </div>
                    <div :class="$style.formItem">
                        <label for="itemCost">Item cost</label> 
                        <input type="text" id="itemCost">
                    </div>
                </form>
                <div :class="$style.mustHaveWrapper">
                    <label for="mustHave">Is it a must-have</label><input type="checkbox" id="mustHave">
                </div>
                <button :class="$style.addItemBtn">Add item</button>
            </div>
            <button :class="$style.generateValueBtn">Generate Max Value!</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'App',

}
</script>

<style module src="@/App.css">

</style>
