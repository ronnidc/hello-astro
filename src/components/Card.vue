<template>
	<article class="card">
		<component :is="href ? 'a' : 'div'" :href="href">
			<h2>
				{{ title }}
				<span v-if="href">&rarr;</span>
			</h2>
			<p v-if="body">
				{{ body }}
			</p>
			<template v-else>
				<slot />
			</template>
		</component>
	</article>
</template>

<script>
export default {
	props: {
		title: String,
		body: String,
		href: String
	}
}
</script>

<style scoped>
.card {
	display: flex;
	padding: 1px;
	border-radius: 7px;
	background-color: #23262d;
	box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.1);
}
.card > a, 
.card > div {
	width: 100%;
	text-decoration: none;
	line-height: 1.4;
	padding: calc(1.5rem - 1px);
	border-radius: 8px;
	color: white;
	background-color: #23262d;
	background-image: none;
	background-size: 400%;
	background-position: 100%;
	transition: background-position 0.6s cubic-bezier(0.22, 1, 0.36, 1);
	opacity: 0.8;
}

h2 {
	margin: 0;
	font-size: 1.25rem;
	transition: color 0.6s cubic-bezier(0.22, 1, 0.36, 1);
}
p {
	margin-top: 0.5rem;
	margin-bottom: 0;
}
.card a:hover, .card a:focus-within {
	background-position: 0;
	background-image: var(--accent-gradient);
}
.card a:hover h2, .card a:focus-within h2 {
	color: rgb(var(--accent-light));
}
</style>