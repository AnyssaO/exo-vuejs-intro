<script>
import { ref, computed } from 'vue';

export default {
  props: {
    options: {
      type: Array,
      required: true,
    },
  },
  setup(props) {
    const searchTerm = ref('');
    const filteredOptions = computed(() => {
      return props.options.filter(option =>
        option.label.toLowerCase().includes(searchTerm.value.toLowerCase())
      );
    });

    const selectOption = (option) => {
      // Gérer la sélection de l'option ici
      console.log(option);
    };

    return { searchTerm, filteredOptions, selectOption };
  },
};
</script>

<template>
    <div>
      <input 
        type="text" 
        v-model="searchTerm" 
        @input="filterOptions" 
        placeholder="Rechercher..." 
        aria-label="Rechercher une option"
      />
      <ul v-if="filteredOptions.length">
        <li 
          v-for="(option, index) in filteredOptions" 
          :key="option.value"
          @click="selectOption(option)" 
          @keydown.enter="selectOption(option)"
          tabindex="0"
        >
          {{ option.label }}
        </li>
      </ul>
    </div>
  </template>
  