<template>
  <div class="container" :class="{ darkCommerce: darkTheme }">
    <header>
      <div class="right">
        <h2 class="page">Shop</h2>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16px"
          height="16px"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="align-text-top feather feather-home"
        >
          <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path>
          <polyline points="9 22 9 12 15 12 15 22"></polyline>
        </svg>
        <h5>ECommerce</h5>
        <h5>Shop</h5>
      </div>
      <div class="left">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="14px"
          height="14px"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="feather feather-settings"
        >
          <circle cx="12" cy="12" r="3"></circle>
          <path
            d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1 0 2.83 2 2 0 0 1-2.83 0l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83 0 2 2 0 0 1 0-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 0-2.83 2 2 0 0 1 2.83 0l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 0 2 2 0 0 1 0 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"
          ></path>
        </svg>
      </div>
    </header>
    <div class="top">
      <p>Filters</p>
      <div class="out">
        <p><span>{{products.length}}</span> results found</p>
        <div class="in">
          <div class="featured">
            <p>Featured</p>
            <img src="./../assets/list.svg" alt="" />
          </div>
          <div class="view">
            <div class="left">
              <svg
                data-v-15eba8c6=""
                xmlns="http://www.w3.org/2000/svg"
                width="18px"
                height="18px"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-grid"
              >
                <rect
                  data-v-15eba8c6=""
                  x="3"
                  y="3"
                  width="7"
                  height="7"
                ></rect>
                <rect
                  data-v-15eba8c6=""
                  x="14"
                  y="3"
                  width="7"
                  height="7"
                ></rect>
                <rect
                  data-v-15eba8c6=""
                  x="14"
                  y="14"
                  width="7"
                  height="7"
                ></rect>
                <rect
                  data-v-15eba8c6=""
                  x="3"
                  y="14"
                  width="7"
                  height="7"
                ></rect>
              </svg>
            </div>
            <div class="right">
              <svg
                data-v-15eba8c6=""
                xmlns="http://www.w3.org/2000/svg"
                width="18px"
                height="18px"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="feather feather-list"
              >
                <line data-v-15eba8c6="" x1="8" y1="6" x2="21" y2="6"></line>
                <line data-v-15eba8c6="" x1="8" y1="12" x2="21" y2="12"></line>
                <line data-v-15eba8c6="" x1="8" y1="18" x2="21" y2="18"></line>
                <line data-v-15eba8c6="" x1="3" y1="6" x2="3.01" y2="6"></line>
                <line
                  data-v-15eba8c6=""
                  x1="3"
                  y1="12"
                  x2="3.01"
                  y2="12"
                ></line>
                <line
                  data-v-15eba8c6=""
                  x1="3"
                  y1="18"
                  x2="3.01"
                  y2="18"
                ></line>
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="main">
      <filters @range="range" @changeBrand="changeBrand" :ratings ="rating"/>
      <products :main ="products" @search="search"/>
    </div>
  </div>
</template>

<script>
import Filters from "./filters.vue";
import products from "./products.vue";

export default {
  components: {
    Filters,products
  },
  props:["darkTheme"],
  data(){
    return{
        data:[],
        word:"",
        min:0,
        max:30000,
        brand:"all",
        num:[]
    }
  },
  mounted(){
    fetch('http://localhost:3000/products')
       .then(res => res.json())
       .then(data => this.data = data)
       .catch(err => console.log(err.message))
  },
  computed:{
    products() {
      return this.data.slice()
      .filter(product => product.name.toLowerCase().includes(this.word))
      .filter(product => product.price >= this.min && product.price <= this.max)
      .filter(product => this.brand == "all" || product.brand == this.brand);
    },
    rating(){
      for(var i=3;i>=0;i--){
        this.num[i] = this.products.filter(product => product.rating == i+1).length;
      }
      this.num[3] += this.products.filter(product => product.rating == 5).length;
      for(var i=2;i>=0;i--){
        this.num[i] += this.num[i+1];
      }
      return this.num.reverse();
    }
  }
  ,methods:{
    search(e){
      this.word = e;
    },
    range(min,max){
      this.min = min;
      this.max = max;
    },
    changeBrand(brand){
      this.brand = brand;
    }
  }
};
</script>

<style lang="scss" scoped>
// .darkCommerce{
//     background: #161d31!important;
// }
.container {
  width: 80%;
  transition: width .2s;
  right: 0;
  background: #f8f8f8;
  position: absolute;
  padding: 110px 29px 0px 35px;
  box-sizing: border-box;
}
header {
  display: flex;
  justify-content: space-between;
  .right {
    display: flex;
    h2,
    h5 {
      margin: 0;
      color: #9186f191;
    }
    h2 {
      color: #636363;
      font-weight: 300;
      position: relative;
      margin-right: 30px;
      &::after {
        content: "";
        position: absolute;
        width: 1px;
        height: 55%;
        background: #d6dce1;
        right: -15px;
      }
    }
    svg {
      margin-top: 5px;
      stroke: #7367f0;
    }
    h5 {
      margin-left: 30px;
      margin-top: 7px;
      position: relative;
      &::before {
        content: "";
        width: 14px;
        height: 14px;
        background-image: url("./../assets/list.svg");
        position: absolute;
        left: -22px;
      }
    }
  }
  .left {
    width: 38px;
    height: 38px;
    background: #7367f0;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: box-shadow 0.5s;
    cursor: pointer;
    &:hover {
      box-shadow: 0 8px 25px -8px #7367f0;
    }
    svg {
      stroke: white;
    }
  }
}
.top,
.out,
.in {
  display: flex;
  justify-content: space-between;
  p {
    color: #7b768c;
  }
  .out {
    width: 70%;
  }
  .in {
    width: 35%;
  }
  .featured {
    width: 130px;
    height: 35px;
    border: 1px solid #7367f0;
    border-radius: 6px;
    padding: 8px 20px;
    padding-right: 10px;
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    cursor:pointer;
    transition: background-color .5s;
    &:hover {
        background: rgba(235, 233, 233, 0.801);
    }
    p {
      margin: 0;
    }
    img {
      width: 20px;
      transform: rotate(90deg);
    }
  }
  .view {
    width: 80px;
    height: 33px;
    border: 1px solid #7367f0;
    border-radius: 5px;
    display: flex;
    overflow: hidden;
    svg {
      stroke: #7367f0;
    }
    .left,
    .right {
      display: flex;
      justify-content: space-evenly;
      align-items: center;
      width: 50%;
      height: 100%;
      transition: background-color 0.5s;
      background: white;
      cursor: pointer;
      &:hover {
        background: rgba(235, 233, 233, 0.801);
      }
    }
    .left {
      border-right: 1px solid #7367f0;
    }
  }
}
.box{
  box-shadow: 0 4px 24px 0 rgb(34 41 47 / 10%);
  border-radius: 7px;
  padding:20px;
}
.main{
  display: flex;
  justify-content: space-between;
  width: 100%;
}

@media screen and (max-width:1200px){
  .container{
    width: 100%;
  }
}
</style>