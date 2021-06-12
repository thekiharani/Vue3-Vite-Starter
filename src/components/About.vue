<template>
    <h1 class="font-bold p-4 text-2xl">About {{ name }}</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At, ipsa. Iure unde error suscipit corrupti corporis saepe dolores quos consequatur ipsam expedita pariatur autem adipisci facere nulla, consequuntur in numquam, eaque ex cum laborum ipsa. Itaque consequuntur, dolorum ullam fugit qui velit ab mollitia cumque odit hic incidunt. Inventore doloribus unde qui nisi assumenda tenetur odit corporis itaque, fugit ducimus? Quibusdam distinctio consectetur, non obcaecati possimus amet illo odio vel hic dignissimos eligendi quasi iste id neque reprehenderit? Culpa provident saepe accusamus voluptatibus quod quia expedita in animi adipisci? Recusandae asperiores eius harum excepturi qui quasi, quibusdam nulla vero tenetur corrupti totam quae. Dolorum minima voluptatem deleniti laborum! Velit laboriosam reprehenderit aspernatur incidunt sunt id corrupti ea ipsa, vel, odit officiis commodi enim laborum recusandae ullam repellendus. Ut tempora nam alias excepturi dolorum animi aut officia, consequuntur saepe commodi ipsum corporis non laudantium quis necessitatibus cum expedita, obcaecati earum quisquam error perferendis. Ad aperiam qui explicabo fugiat tempora, reprehenderit modi ipsam voluptatibus rerum nihil illum error blanditiis laboriosam alias numquam, quibusdam necessitatibus libero quisquam quos molestias culpa repudiandae. Dolorum explicabo reprehenderit tempore iure, animi veritatis eveniet. Architecto enim, modi minima sint similique reprehenderit numquam voluptate quis optio corrupti, necessitatibus maiores!</p>

    <div class="text-center my-6">
        <button @click="back" class="px-6 py-2 bg-purple-700 text-white rounded-full w-full">Go Back</button>
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

const back = () => {
    router.push('/')
}
</script>
