<script setup>
import {ref, onMounted} from 'vue'

const user = ref();

onMounted(async () => {
    console.log('Component mounted.')

    const res = await axios.get('/api/user');
    user.value = await res.data;
    console.log(user.value);
})
</script>

<template>
    <div class="py-12">
        <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
            <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900 dark:text-gray-100">
                    <h2 class="text-2xl font-bold mb-3">Example Vue Component</h2>

                    I'm an example component.

                    <div>
                        Name: {{ user?.name }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
