<template>

  <!--Step 3 use the component-->
<div class="wrapper">
  <MyHeader bookName="EVENTOPIA" authorName="Your Guide to Local Happenings" yourName="Advika Kairamkonda"/> 
  <BookBox :books=books />
</div>
</template>

<script>
// Step: 1 Import the components
import MyHeader from './components/MyHeader.vue'
import BookBox from './components/BookBox.vue'


export default{
  name: 'App',

  // Step 2: Register the components
  components:{
    MyHeader,
    BookBox
  },
  data(){
    return {
      books: []
    }
  },
  methods:{
    //promoises
    async fetchbooks(){
      const res = await fetch('https://webdatabase-finalproject-node.onrender.com/api');
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created(){
      this.books = await this.fetchbooks();
  }

  // data() => this.data books
  // method => this.method => fetchbook
  // life cycle hooks created() => call our method here

}
</script>


<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}

div{
  margin-bottom: 0.5em;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: white;
  margin-top: 60px;
  
}

.wrapper {
  background-color: #2a3439;
  padding: 20px;
  border-radius: 10px; /* Optional: adds rounded corners to the wrapper */
  text-align:center;
  width: 80%;
  margin: auto;
  
   
}

</style>



