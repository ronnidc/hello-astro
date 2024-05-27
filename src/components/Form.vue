<template>
	<div>
	  <h3>{{ title }}</h3>
	  <input v-model="title" placeholder="Type here to change the title" />
	</div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  let title = ref('Titles can change');
  
  watch(title, (newTitle) => {
	console.log('Title changed:', newTitle);
  });
  </script>
  
  <style scoped>
  h3 {
	font-size: 1em;
	margin-bottom: 0.5em;
  }
  
  input {
	padding: 0.5em;
	font-size: 1rem;
	width: 100%;
	border: none;
	border-radius: 8px;
	font-family: monospace;
  }
  </style>
  