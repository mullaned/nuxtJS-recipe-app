<template>
    <section class="single-recipe">
        <h1>{{ recipe.title }}</h1>
        <div>
            <img :src="recipe.thumbnail" alt="recipe" class="thumbnail">
        </div>
        <p>{{recipe.descriptionText}}</p>
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
                            id:"1",
                            title:"pizza",
                            previewText: "delicious Pizza",
                            thumbnail:"https://www.gannett-cdn.com/media/2018/07/17/IAGroup/DesMoines/636674359927753055-0717-NEW-STATEFAIR-FOODS-00029.jpg",
                            descriptionText:"this is great"
                        },
                        {
                            id:"2",
                            title:"burger",
                            previewText: "delicious burger",
                            thumbnail:"https://www.telegraph.co.uk/content/dam/business/2018/01/17/pizza_trans_NvBQzQNjv4BqZgEkZX3M936N5BQK4Va8RWtT0gK_6EfZT336f62EI5U.jpg",
                            descriptionText:"this is great"
                        }
                    ].find(el => el.id === context.params.id)
                })
            },1500)
        })
    }
    
}
</script>


<style scoped>
.single-recipe{
        display: flex;  
        flex-flow: column;
        justify-content: center;
        align-items: center;
    }

.thumbnail{
        background-position: center;
        background-size: cover;
        width: 100%;
        height: 200px;    
    }
</style>
