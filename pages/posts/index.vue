<template>
    <div v-if="posts">
            <h1 class="posttitulo text-center ">¿CUÁL VA A SER TU PRÓXIMO NISSAN?</h1>
        <Card
            v-for= "post in posts.results"
            :key="post.id"
            :id = "post.id"
            :model = "post.model"
            :detail = "post.detail"
            :gallery = "post.gallery"
            :amount = "post.amount"
            :currency = "post.currency"
        />
    </div>
</template>
<style>
.posttitulo{
    background:#D8D8D8;
    color:white;
    height:150px;
    font-family:arial black;
}
@media (max-width: 439px) {
    h1{
        font-size:25px;
    }
}
</style>
<script>
    import Card from '../../components/Card'
    export default{
        components:{
            Card
        },
        head(){
            return{
                title:'Nissan Store',
            }
        },
        data(){
            return {
                posts: null,
                search:''
            }
        },
        created(){
            this.fetchCars();

        },
        computed:{
            postsId(){
                return
                this.$route.params.id
            },
            getPost(){
                if(this.posts==null)
                return null
                else
                {
                    return this.posts.results.find((item)=>
                        item.id === this.postsId
                    )
                }
            },
        },
        methods:{
            async fetchCars(){
                this.$route.params;
                this.posts = await this.$axios.$get('https://4my1q6hsyo.api.quickmocker.com/product',{headers:{Accept:'application/json',Authorization:'Bearer qwertyuiopasdfghjklzxcvbnm123456'}})
                console.log(this.posts);
            }
        }
    }
</script>