<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Nhoque de Frango",
              previewText: "Gosotoso demais!",
              descriptionText: "Essa receita é deliciosa",
              thumbnail:
                "https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
            },
            {
              id: "2",
              title: "Pizza de Frango",
              previewText: "Delicia demais!",
              descriptionText: "Essa receita é deliciosa",
              thumbnail:
                "https://www.receitasnestle.com.br/images/default-source/recipes/nhoque_molho_tomatef4efa01f83b963b0a6c0ff0300205b53.jpg"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 1500);
    });
  }
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-content: center;
  text-align: center;
  padding: 30px;
}
.recipe-image{
    width: 100%;
}
</style>
