<script setup>
import {computed, reactive, ref} from "vue";

const selectedUsers=ref([]);

const users = ref([
  "Abdul-Azeem",
  "Mahmud",
  "Habeeb",
  "Tunji"
]);

const computedSelectedUsers = computed(()=>{
  return selectedUsers.value.join(',');
});

const update = (user) => {
  selectedUsers.value.push(user);
}

</script>

<template>
  <main class="grid gap-3">
    <h1 class="text-5xl">My Test Page</h1>
    <button class="btn btn-accent">
      checked
    </button>

    <div>
      {{computedSelectedUsers}}
    </div>

    <div class="flex gap-8 items-center">
      <label
        class="bg-neutral-content block p-3 border rounded-lg text-black cursor-pointer
               hover:bg-neutral-200 transition-colors duration-200"
        v-for="(user, index) in users"
        :key="index"
      >

         <input type="checkbox" v-model="selectedUsers" :value="user"/>
         {{user}}
      </label>
    </div>
  </main>
</template>

<style scoped>

</style>
