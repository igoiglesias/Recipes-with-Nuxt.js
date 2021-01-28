<template>
  <section class="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>
import Recipe from "@/components/Recipe";
export default {
  methods: {},
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "1",
              title: "Nhoque de Frango",
              previewText: "Gosotoso demais!",
              thumbnail:
                "https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
            },
            {
              id: "2",
              title: "Pizza de Frango",
              previewText: "Delicia demais!",
              thumbnail:
                "https://www.receitasnestle.com.br/images/default-source/recipes/nhoque_molho_tomatef4efa01f83b963b0a6c0ff0300205b53.jpg"
            }
          ]
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.recipes {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
