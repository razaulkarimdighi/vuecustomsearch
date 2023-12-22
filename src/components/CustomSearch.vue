   <template>
    <h3>POSTS</h3>
    <input type="text" placeholder="search" v-model="search">
   <div v-for="post in searchTerm" :key="post.id">
            <h3>{{ post.id }}</h3>
            <h2>{{ post.title }}</h2>
            <p>{{ post.body}}</p>
            <hr>
    </div>
   </template>
    <script>
   import axios from 'axios'
        export default{
           
            data(){
                return{
                    posts: [],
                    search:''
                }
            },

            computed:{
                            searchTerm(){
                                return this.posts.filter(post=>{
                                    return post.title.match(this.search)
                                })
               }
            },
            
            
            created(){
                axios.get('https://jsonplaceholder.typicode.com/posts')
                .then(a => {
                     console.log((a))
                    this.posts = a.data
                })
                .catch(error => {
                    console.log(error)
                })
            }
            

        }
            
    </script>
    <style>
    
    </style>