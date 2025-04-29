<script setup>
import { ref } from "vue";
import CrochetPart from "@/components/CrochetPart.vue";

const id = ref(0);
const name = ref("ProjectName");
const newPartName = ref("");
function createPart() {
  parts.value.push({
    key: id.value++,
    name: newPartName.value === "" ? "New part" : newPartName,
    rows: 0,
    stitches: 0
  });
  newPartName.value = "";
}

const parts = ref([
  {
    key: 111,
    name: "Head",
    rows: 0,
    stitches: 0,
  },
  {
    key: 222,
    name: "Body",
    rows: 0,
    stitches: 0,
  },
]);
</script>

<template>
  <h2>{{ name }}</h2>
  <input v-model="newPartName" placeholder="New Part Name" />
  <button @click="createPart">Create</button>
  <CrochetPart v-for="part in parts" :key="part.key" v-bind="part" />
</template>

<style scoped></style>
