<script lang="ts" setup>
import {RouterLink, RouterView} from 'vue-router'
import NavBar from "@/components/NavBar.vue";
</script>

<template>

	<nav-bar msg="test"/>

	<router-view v-slot="{ Component }">
		<keep-alive>
			<component :is="Component" v-if="$route.meta.keepAlive" :key="$route.name"/>
		</keep-alive>
		<component :is="Component" v-if="!$route.meta.keepAlive" :key="$route.name"/>
	</router-view>

</template>

<style lang="scss">
html * {
	// 此处若使用 !important 会覆盖部分组件库的 icon
	font-family: LXGW WenKai Lite, serif;
}

@media (min-width: 1024px) {
}
</style>
