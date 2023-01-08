<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import Player from './components/Player.vue'
</script>

<template>
	<body>
		
		<RouterView />
		<Player/>
	</body>
</template>

<style lang="scss">
@import "./scss/base.scss"




</style>
