
<template>
    <div class="col-md-12 p-5" v-if="showFlexboxComponent" style="padding: 50px 200px !important; border-radius: 10px;">
        <div class="text-center mb-5">
            <h1 class="text-success">Flexbox CSS Layout</h1>
        </div>
        <div class="form-group">
            <label>Child Count:</label>
            <input type="number" min="1" v-model="childCount" class="form-control">
        </div>
        <div class="form-group mt-3">
            <label>Flex Direction:</label>
            <select class="form-select" v-model="flexDirection">
                <option value="">-- Please select --</option>
                <option value="flex-row">row</option>
                <option value="flex-row-reverse">row-reverse</option>
                <option value="flex-column">column</option>
                <option value="flex-column-reverse">column-reverse</option>
            </select>
        </div>
        <div class="form-group mt-3">
            <label>Flex Wrap:</label>
            <select class="form-select" v-model="flexWrap">
                <option value="">-- Please select --</option>
                <option value="flex-nowrap">nowrap</option>
                <option value="flex-wrap">wrap</option>
                <option value="flex-wrap-reverse">wrap-reverse</option>
            </select>
        </div>
        <div class="form-group mt-3">
            <label>Justify Content:</label>
            <select class="form-select" v-model="flexJustifyContent">
                <option value="">-- Please select --</option>
                <option value="justify-content-start">flex-start</option>
                <option value="justify-content-end">flex-end</option>
                <option value="justify-content-center">center</option>
                <option value="justify-content-around">space-around</option>
                <option value="justify-content-evenly">space-evenly</option>
                <option value="justify-content-between">space-between</option>
            </select>
        </div>
        <div class="form-group mt-3">
            <label>Align Items:</label>
            <select class="form-select" v-model="flexAlignItems">
                <option value="">-- Please select --</option>
                <option value="align-items-stretch">stretch</option>
                <option value="align-items-baseline">baseline</option>
                <option value="align-items-center">center</option>
                <option value="align-items-start">flex-start</option>
                <option value="align-items-end">flex-end</option>
            </select>
        </div>
        <div class="form-group mt-3">
            <label>Align Content:</label>
            <select class="form-select" v-model="flexContent">
                <option value="">-- Please select --</option>
                <option value="align-content-center">center</option>
                <option value="align-content-start">flex-start</option>
                <option value="align-content-end">flex-end</option>
                <option value="align-content-around">space-around</option>
                <option value="align-content-evenly">space-evenly</option>
                <option value="align-content-between">space-between</option>
            </select>
        </div>
        <div class="mt-5">
            <div style="width: 100%; height: 400px;"
                class="bg-dark bg-opacity-10 d-flex border border-3 border-dark" :class="flexClass">
                <div v-for="child in childCount" :key="child"
                    class="p-5 bg-primary text-center d-flex align-items-center justify-content-center fs-1 text-white border border-2 border-warning">
                    {{ child }}
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed} from 'vue'

const childCount = ref(1)
const flexDirection = ref('')
const flexWrap = ref('')
const flexJustifyContent = ref('')
const flexAlignItems = ref('')
const flexContent = ref('')

const flexClass = computed(() => {
    let classes = [
        flexDirection.value,
        flexWrap.value,
        flexJustifyContent.value,
        flexAlignItems.value,
        flexContent.value
    ]

    return classes.join(' ')
})

const { showFlexboxComponent } = defineProps(['showFlexboxComponent'])

</script>