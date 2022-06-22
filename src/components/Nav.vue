<template>

    <div id="nav">
        <router-link to="/home">Home</router-link>
        <router-link to="/store">Store</router-link>
        <router-link to="/messages">Message Feed</router-link>
        <router-link :to="{name: 'about',
          params: {user: 'von Kimo'}}">About</router-link>
        <RouterView/>
    </div>
</template>

<style>
    *{
        background-color: #4b4b4b;
        color: white;
        font-family: "Roboto Light",sans-serif;

    }
        h2, h1{
            padding-top: 20px;
            margin-left: 10px;
        }

    #nav {
        font-weight: bold;
        font-size: 20px;
        display: inline-block;
        padding: 20px;
        width: 100%;
    }

    #nav a {
        color: white;
        margin: 10px 0 0 10px;
    }


</style>