<script setup>
import {ref} from "vue";

const props = defineProps({
  name: String,
  rows: Number,
  stitches: Number,
});

const name = ref(props.name);
const rows = ref(props.rows);
const stitches = ref(props.stitches);

function addRow() {
  rows.value++;
  stitches.value = 0;
}

</script>

<template>
  <div>
    <h3>{{ name }}</h3>
    <div>
      <p>Rows: {{ rows }}, Stitches: {{ stitches }}</p>
    </div>
    <button @click="addRow">Add Row</button>
    <button @click="stitches++">Add Stitch</button>
  </div>
</template>

<style scoped></style>
