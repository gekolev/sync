<template>
  <div>
      <main>
        <Item v-for="(image, i) in image_list" :key="i" :image="image"/>
      </main>
  </div>
</template>

<script>
import Item from '../components/Item.vue';
export default {
	name: "Scroll",
	data() {
		return {
			image_list: [],
		};
	},
	components: {
		Item,
	},
	methods: {
		getImage() {
			const image_links = [
          "https://images.unsplash.com/photo-1506749841726-3df2e72b9564?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80",
          "https://images.unsplash.com/photo-1511104286249-cade2ff54588?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80",
          "https://images.unsplash.com/photo-1578351661377-f7353fd9a9b9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=735&q=80",
          "https://images.unsplash.com/photo-1541190041139-c5f28bdfe5d1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1471&q=80",
          "https://images.unsplash.com/photo-1515572090192-ba877b71676e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1483&q=80",
          "https://images.unsplash.com/photo-1583144584182-1717fab24b1e?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1631336682619-0dce5d3b596b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1631336682619-0dce5d3b596b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1468657988500-aca2be09f4c6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1519813416611-f00c34dfb981?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1624&q=80",
          "https://images.unsplash.com/photo-1585670089589-2f6cd2719a27?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1515446808777-87f69cb475aa?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80",
          "https://images.unsplash.com/photo-1543053976-5fd9336b6de0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"

			];
			const image = [];
			for (let i = 0; i < 10; i++) {
				image.push({
					title: image_links[
						Math.floor(Math.random() * image_links.length)
					],
					description:
						"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
				});
			}
			return image;
		},
		handleScroll() {
			if (
				window.scrollY + window.innerHeight >=
				document.body.scrollHeight - 50
			) {
				const new_image = this.getImage();
				this.image_list = [...this.image_list, ...new_image];
			}
		},
	},
	mounted() {
		this.image_list = this.getImage();
		window.addEventListener("scroll", this.handleScroll);
	},
};
</script>

<style lang="scss">
@import "~assets/scss/variables.scss";
body{
  margin:0;
}
main{
  background-color:black;
}

</style>