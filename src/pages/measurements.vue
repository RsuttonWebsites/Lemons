<template>
  <v-container>
    <h1>Measurement Tools</h1>
    <div v-for="tool in tools" :key="tool.label">
      <v-text-field
        :label="tool.label"
        variant="outlined"
        v-model="tool.input"
        type="number"
      />
      <div>{{ tool.resultLabel }}: <strong>{{ tool.output }}</strong></div>
      <v-divider class="my-4" />
    </div>

    <div></div>
  </v-container>
</template>

<script setup>
import { reactive, computed } from 'vue';

const tools = reactive([
  {
    label: 'Centimeters → Inches',
    resultLabel: 'Inches',
    input: '',
    output: computed(() =>
      tools[0].input !== ''
        ? (parseFloat(tools[0].input) * 0.393701).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Inches → Centimeters',
    resultLabel: 'Centimeters',
    input: '',
    output: computed(() =>
      tools[1].input !== ''
        ? (parseFloat(tools[1].input) / 0.393701).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Inches → Feet',
    resultLabel: 'Feet',
    input: '',
    output: computed(() =>
      tools[2].input !== ''
        ? (parseFloat(tools[2].input) / 12).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Feet → Inches',
    resultLabel: 'Inches',
    input: '',
    output: computed(() =>
      tools[3].input !== ''
        ? (parseFloat(tools[3].input) * 12).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Feet → Meters',
    resultLabel: 'Meters',
    input: '',
    output: computed(() =>
      tools[4].input !== ''
        ? (parseFloat(tools[4].input) * 0.3048).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Meters → Feet',
    resultLabel: 'Feet',
    input: '',
    output: computed(() =>
      tools[5].input !== ''
        ? (parseFloat(tools[5].input) / 0.3048).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Centimeters → Meters',
    resultLabel: 'Meters',
    input: '',
    output: computed(() =>
      tools[5].input !== ''
        ? (parseFloat(tools[5].input) / 100).toFixed(2)
        : '—'
    ),
  },
  {
    label: 'Meters → Centimeters',
    resultLabel: 'Centimeters',
    input: '',
    output: computed(() =>
      tools[6].input !== ''
        ? (parseFloat(tools[6].input) * 100).toFixed(2)
        : '—'
    ),
  },
]);
</script>