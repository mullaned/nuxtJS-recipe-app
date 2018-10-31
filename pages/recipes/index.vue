<template>
   <section class="recipes">
       <Recipe
            v-for="recipe in recipes"
            :key="recipe.id"
            :thumbnail="recipe.thumbnail"
            :title="recipe.title"
            :previewText="recipe.previewText"
            :id="recipe.id">
        </Recipe> 
         
       
   </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
    components: {
        Recipe
    },
    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id:"1",
                            title:"pizza",
                            previewText: "delicious Pizza",
                            thumbnail:"https://www.gannett-cdn.com/media/2018/07/17/IAGroup/DesMoines/636674359927753055-0717-NEW-STATEFAIR-FOODS-00029.jpg"
                        },
                        {
                            id:"2",
                            title:"burger",
                            previewText: "delicious burger",
                            thumbnail:"https://www.telegraph.co.uk/content/dam/business/2018/01/17/pizza_trans_NvBQzQNjv4BqZgEkZX3M936N5BQK4Va8RWtT0gK_6EfZT336f62EI5U.jpg"
                        }
                    ]
                })
            },1500)
        })
    }
    
}
</script>


<style scoped>
    .recipes{
        display: flex;
        flex-flow: row wrap;
        justify-content: center;
        align-items: center;
    }

    .recipe{
        box-sizing: border-box;
        width: 280px;
        padding: 8px;
        border: 1px solid #ccc;
        box-shadow: 0 2px 2px #aaa;
        margin: 10px;
    }

    .thumbnail{
        background-position: center;
        background-size: cover;
        width: 100%;
        height: 200px;    
    }
</style>
