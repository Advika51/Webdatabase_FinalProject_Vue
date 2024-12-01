<template>
    

    <div  :class="book.Availability ? 'blue': 'cream' ">
                        <h2>{{book.Title}}</h2>
                        <h4>Event Type : {{book.Event_Type}}</h4>
                        <h4>Description : {{book.Description}}</h4>
                        <h4>Featured Artists : {{book.Featured_Artists}}</h4>
                        <h4>Date and Time : {{book.Date_and_Time}}</h4>
                        <h4>Location : {{book.Location}}</h4>
                        <h4>Ticket Price : {{book.Ticket_Price}}</h4>
                        <h4>Availability : {{book.Availability}}</h4>
                        <img :src="book.Photo" alt="image alt" >
                        <img :src="book.Photo2" alt="image alt" >
                        <img :src="book.Photo3" alt="image alt" >
    </div>
</template>

<script>

export default{
    name: 'SingleBook',
    props:{
        book: Array
    }
}
</script>

<style scoped>

.blue{
    background-color:  #D5E4F4;
}


div{
    
    color: black;
    padding: 2em;
    text-align: center;
    width: 80%;
    margin: auto;
    

}

h2{
    color:brown;
    background-color:#DCDCDC;
    font-weight:bold;
    display: inline-block;
    margin-bottom:10px; 

}

h4{
    margin-top:2.5px;
}


img{
    margin-top:20px;
    margin-right:20px;
    height:120px;
    width:200px;
}

.cream{
background-color:  #FBFAF5!important;

}


</style>