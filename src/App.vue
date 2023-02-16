<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Inter:100,200,300,400,500,700,700i,900&display=swap');

*{
    margin: 0;
    padding: 0;
    list-style: none;
    text-decoration: none;
}

header{
    width: 100vw;
    height: 60px;
    border-bottom: solid 1px rgba(16, 16, 16, 0.1);
    font-family: 'News Cycle', sans-serif;
    font-weight: 400;
    font-style: normal;
    position: fixed;
    top:0;
    z-index:5;

}

header .inner{
    width: 100%;
    height: 100%;
    display: block;
    margin: 0 auto;
    background-color: #823737;
    border: #823737;
}

header .logo{
    display: table;
    height: 100%;
    float: left;
}

header .logo div{
    height: 100%;
    display: table-cell;
    vertical-align: middle;
}

header .logo img{
    height: 55px;
    margin-top: 3px; /* Optical alignment of the logo */
}

header nav{
    float: left;
    margin-left: 5px;
    height: 100%;
}

header nav li{
    display: table;
    height: 100%;
    float: left;
    margin-right: 30px;
}

header nav li:last-of-type{
    margin-right: 0;
}

header nav span {
    display: table-cell;
    vertical-align: middle;
    color: white;
    font-family: 'News Cycle', sans-serif;
    font-weight: bold;
    font-size: 18px;
}

header nav a{
    color: white;
}

body
{
    padding-top:  40px;
    padding-bottom: 60px;
}

/* .switch {
    position: relative;
    display: inline-block;
    margin-left: 20px;
    /* margin-top: 10px; 
    width: 60px;
    height: 28px;
} */
  
  /* Hide default HTML checkbox */
/* .switch input {
    opacity: 0;
    width: 0;
    height: 0;
} */

.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: .4s;
    transition: .4s;
}
  
.slider:before {
    position: absolute;
    content: "";
    height: 22px;
    width: 22px;
    left: 3px;
    bottom: 3px;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
}

input:checked + .slider {
    background-color: #52ce77;
}

input:focus + .slider {
    box-shadow: 0 0 2px #ccc;
}

input:checked + .slider:before {
    -webkit-transform: translateX(32px);
    -ms-transform: translateX(32px);
    transform: translateX(32px);
}

/* Rounded sliders */
.slider.round {
    border-radius: 34px;
    box-shadow: 0 0 2px #ccc;
}

.slider.round:before {
    border-radius: 50%;
    box-shadow: 0 0 2px #ccc;
}


#textarea_input{
    width: 60%;
    height: 250px;
    /* border: none; */
    /* outline: none; */
    margin-top: 10px;
    margin-left: 20px;
    resize: none;
    font-family: 'Inter';
    font-size: 14px;
    padding: 10px;
    background-color: #f5f5f5;
    color: #000;
    border-radius: 5px;
    box-shadow: 0 0 2px #ccc;
}
#toolbar{
    margin-left: 20px;
    /* margin-top: 5px; */
    margin-bottom: 5px;
    /* border-color: #000 */
    /* border:1px solid black; */

}
</style>
