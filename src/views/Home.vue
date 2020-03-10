<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png">
		<HelloWorld msg="Welcome to Your Vue.js App"/>
    <ListFilterSearch id="searchList" :datas='[{name: "Apples"}, {name: "Broccoli"}, {name: "Tomatos"}, {name: "Milk"}, {name: "Eggs"}, {name: "Water"}, {name: "Granola"}, {name: "Bananas"}, {name: "Smoothie"}, {name: "Salat"}, {name: "Yogurt"}]'></ListFilterSearch>
	</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import ListFilterSearch from '@/components/list-filter-search.vue';

export default {
	name: 'Home',
	components: {
		HelloWorld,
		ListFilterSearch
	}
}
</script>
