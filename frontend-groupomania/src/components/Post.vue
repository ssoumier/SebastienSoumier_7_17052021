<template>
<div class="post">
 
<div class="container mt-5 mb-5">
    <div class="row d-flex align-items-center justify-content-center">
        <div class="col-md-6">
            <div class="card card-color">
                <div class="d-flex justify-content-between p-2 px-3">
                    <div class="d-flex flex-row align-items-center"> <img src="https://i.imgur.com/UXdKE3o.jpg" width="50" class="rounded-circle">
                        <div class="d-flex flex-column ml-2 cursor"> <span @click="onSelect(post.UserId)" class="font-weight-bold">{{ post.User.username }}</span> </div>
                    </div>
                    <div @click="onDelete(post.id)" class="d-flex flex-row mt-1 ellipsis">  <font-awesome-icon :icon="['fas', 'times']" />  </div>
                </div> <img :src="post.attachment" class="img-fluid">
                <div class="p-2">
                    <p class="text-justify">{{ post.content}}</p>
                    <hr>
                    <div class="icons d-flex justify-content-around">
                        <!-- <div class="d-flex flex-row icons d-flex align-items-center">   <font-awesome-icon :icon="['far', 'smile']" /> </div> -->
                        <div class="cursor"> <span @click="onLike(post.id)" @dblclick="ondisLike(post.id)"> <font-awesome-icon :icon="['fas', 'thumbs-up']" /> </span> </div>
                        <div>  <span>{{post.likes}} </span> <span><font-awesome-icon :icon="['fas', 'heart']" /> </span></div>
                    </div>
                   
                   
                </div>
            </div>
        </div>
    </div>
</div>

  </div>
</template>

<script>

export default {
   
name: 'Post',
props: {
    post: Object
},
methods : {

   

    onDelete(id) {
        this.$emit('delete-post', id)
    },
    onLike(id) {
        this.$emit('like-post', id)
    },
    ondisLike(id) {
        this.$emit('dislike-post', id)
    },
    onSelect(id) {

   this.$emit('select-post', id)

    },
}
}
</script>

<style>

@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800&display=swap");

body {
    background-color: #eee;
    font-family: "Poppins", sans-serif;
    font-weight: 300
}

.card-color {
    border: none;
    background-color: #fcd6d5!important;;
}
.cursor {
    cursor: pointer
}
.ellipsis {
    color: #a09c9c
}

hr {
    color: #a09c9c;
    margin-top: 4px;
    margin-bottom: 8px
}

.muted-color {
    color: #a09c9c;
    font-size: 13px
}

.ellipsis i {
    margin-top: 3px;
    cursor: pointer
}

.icons {
    font-size: 25px
}

.icons .fa-heart {
    color: red;
    
}

.icons .fa-smile {
    color: yellow;
   
}

.rounded-image {
    border-radius: 50% !important;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50px;
    width: 50px
}

.name {
    font-weight: 600
}

.comment-text {
    font-size: 12px
}

.status small {
    margin-right: 10px;
    color: blue
}

.form-control {
    border-radius: 26px
}

.comment-input {
    position: relative
}

.fonts {
    position: absolute;
    right: 13px;
    top: 8px;
    color: #a09c9c
}

.form-control:focus {
    color: #495057;
    background-color: #fff;
    border-color: #8bbafe;
    outline: 0;
    box-shadow: none   
}


</style>