<template>
    <div class="head-container">
      <div class="img-container">
        <img src="../assets/Images/Icons/Police.png" width="96" height="88" alt="">
      </div>
      <div class="title-container">
        <div class="text">Мобильный терминал данных ЛСПД</div>
        <div class="hello">Добро пожаловать, {{name}}</div>
      </div>
     
      
    </div>
    
  </template>
  
  <script>
  export default {
    name: 'офицер Райдон',
    props: {
      name: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style lang="scss" scoped>
  .head-container{
    background-color: rgb(4,37,79);
    color: white;
    display: flex;
    flex-direction: row;
    
  }
  .title-container {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: center;
    align-items: center;
    .text {
      text-transform: uppercase;
      font-size: 36px;
      text-align: center;

    }
  }
  </style>