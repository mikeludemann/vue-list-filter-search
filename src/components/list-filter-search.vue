<template lang="html">

	<section class="list-filter-search">
		<div class="search--filter--list" :style="searchFilterList">
			<input type="text" :id="id" placeholder="Search" @keyup="filterList" :style="textField"/>
			<ul :style="listContainer">
				<li :style="listElements" v-for="data in datas">{{ data.name }}</li>
			</ul>
		</div>
	</section>

</template>

<script lang="js">

	export default {
		name: 'ListFilterSearch',
		props: {
			datas: {
				type: Array
			},
			id: {
				type: String
			}
		},
		mounted () {

		},
		data () {
			return {

			}
		},
		methods: {
			filterList: function(event){

				var input, filter, list, li, a, i, txtValue;

				input = document.getElementById(this.id);

				filter = input.value.toUpperCase();

				list = input.parentElement.children[1];

				li = list.getElementsByTagName("li");

				for (i = 0; i < li.length; i++) {

					txtValue = li[i].textContent || a.innerText;

					if (txtValue.toUpperCase().indexOf(filter) > -1) {

						li[i].style.display = "";

					} else {

						li[i].style.display = "none";

					}

				}

			}
		},
		computed: {
			searchFilterList: function(){
				return {
					padding: "20px",
					maxWidth: "200px",
					margin: "auto"
				};
			},
			textField: function(){
				return {
					lineHeight: "2",
					fontSize: "16px",
					height: "auto",
					paddingLeft: "20px",
					width: "94%",
					marginBottom: "5px"
				};
			},
			listContainer: function(){
				return {
					margin: "0",
					padding: "0"
				};
			},
			listElements: function(){
				return {
					listStyle: "none",
					border: "1px solid #ccc",
					marginTop: "-1px",
					lineHeight: "2",
					padding: "5px 0px 5px 20px",
					background: "#fff",
					width: "95%",
					textAlign: "left"
				};
			}
		}
}


</script>

<style scoped lang="scss">
	.list-filter-search {

	}
</style>
