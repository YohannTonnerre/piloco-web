<template>
	<span class="player-card">
		<img :src="`/img/beer${index}.svg`" alt="" />
		<span>{{ playerName }}</span>
	</span>
</template>

<script>
export default {
	props: {
		playerName: String,
		index: Number
	}
}
</script>

<style>
</style>
