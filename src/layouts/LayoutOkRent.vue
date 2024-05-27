<template>
<!doctype html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta name="description" content="Astro description" />
		<meta name="viewport" content="width=device-width" />
		<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
		<meta name="generator" content="Astro.generator" />
		<title>{{ pageTitle }}</title>
	</head>
	<body>
		<slot />
	</body>
</html>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    pageTitle: {
        type: String,
        required: true
    }
});
</script>

<style>
:root {
	--accent: 136, 58, 234;
	--accent-light: 224, 204, 250;
	--accent-dark: 49, 10, 101;
	--accent-gradient: linear-gradient(
		45deg,
		rgb(var(--accent)),
		rgb(var(--accent-light)) 30%,
		white 60%
	);
}
html {
	font-family: system-ui, sans-serif;
	background: #13151a;
	background-size: 224px;
}

*, *::before, *::after {
	box-sizing: border-box;
}
code {
	font-family:
		Menlo,
		Monaco,
		Lucida Console,
		Liberation Mono,
		DejaVu Sans Mono,
		Bitstream Vera Sans Mono,
		Courier New,
		monospace;
}
</style>