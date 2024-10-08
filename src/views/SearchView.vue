<template>
    <AutocompleteSelectComponent :options="options" />
  </template>
  
  <script>
import AutocompleteSelectComponent from '@/components/AutocompleteSelectComponent.vue';

  
  export default {
    components: { AutocompleteSelectComponent },
    data() {
      return {
        options: [
          { label: 'orange', value: 1 },
          { label: 'poire', value: 2 },
          { label: 'pomme', value: 3 },
          { label: 'banane', value: 4 },
          { label: 'fraise', value: 5 },
          { label: 'pêche', value: 6 },
          { label: 'citron', value: 7 },
          // Ajoute d'autres options ici
        ],
      };
    },
  };
  </script>
  