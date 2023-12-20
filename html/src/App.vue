<template>
  <div id="app">
    <div class="main-container">
      <Header :name="name"/>
      <div class="bodypage-container">
        <div class="navigation-container">
          Навигация
           
          <ul>Кнопка 1</ul>
          <ul>Кнопка 2</ul>
          <ul>Кнопка 3</ul>
          <ul>Кнопка 4</ul>
          <ul>Кнопка 5</ul>

        </div>
        <div class="maincontextcontainer">я главная часть</div>
        
      </div>
      
      <div class="footer">я футер</div>
    </div>
    
  </div>
</template>

<script>
import Header from './components/Header.vue';


export default {
  name: 'app',
  components: {
    
    Header
  },
  data() {
    return {
      name:"офицер Томпсон",
      characters:[
        {"citizenID":"fdsfsdf", "name":"AlexLutyi", },
        {"citizenID":"fdsfsdf", "name":"AlexLutyi", },
        {"citizenID":"fdsfsdf", "name":"AlexLutyi", },
        {"citizenID":"fdsfsdf", "name":"AlexLutyi", },
        {"citizenID":"fdsfsdf", "name":"AlexLutyi", },
      ],
    };
  },
  destroyed() {
    window.removeEventListener('message', this.listener);
  },
  mounted() {
    this.listener = window.addEventListener(
      'message',
      event => {
        const item = event.data || event.detail;
        if (this[item.type]) {
          this[item.type](item);
        }
      },
      false,
    );
  },
  methods: {},
};
</script>

<style lang="scss">
/* Want nice animations? Check out https://github.com/asika32764/vue2-animate */
/* @import 'https://unpkg.com/vue2-animate/dist/vue2-animate.min.css'; */
.main-container{
  display: flex;
  flex-direction: column;
  min-height: 95vh;
  .bodypage-container{
    flex-grow: 1;
    display: flex;
    flex-direction: row;
    
    .navigation-container{
      flex-grow: 1;
      border: 1px black solid;
      
    }
    .maincontextcontainer{
      flex-grow: 20;
      border: 1px black solid;
    }

    .footer{
      flex-shrink: 0;
    }

  }
}
</style>
