<template>
    <h1 class="font-extrabold text-3xl mb-4">Home</h1>
    <p class="mb-6">Name is the store is: {{ name }}</p>

    <div class="flex space-x-0">
        <input
            v-model="newName"
            type="text"
            class="
                px-4
                py-2
                border border-gray-500
                rounded-l-full
                focus:border-purple-700 focus:outline-none
            "
            placeholder="Name..."
        />
        <button
            @click="saveName"
            class="
                px-6
                py-2
                bg-purple-700
                text-white
                rounded-r-full
                focus:outline-none
            "
        >
            Save
        </button>
    </div>
</template>

<script setup>
import { computed, ref } from 'vue'
import { useStore } from 'vuex'
import { useRouter } from 'vue-router'

const store = useStore()
const router = useRouter()

const name = computed(() => {
    return store.state.user.name
})

const newName = ref('')

const saveName = () => {
    store.dispatch('saveName', newName.value)
    newName.value = ''
    router.push('/about')
}
</script>
