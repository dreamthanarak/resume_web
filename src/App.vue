<!-- <template>
  <div class="section" data-theme="luxury">
    <div class="flex h-screen">
      <div class="m-auto">
        <h3 class="text-8xl">Resume</h3>
        
          <div class="avatar">
            <div class="w-24 rounded-full">
              <img src="/images/catmeaw.jpg" />
            </div>
          </div>
          <div class="flex bg-base-200">name: Thanarak banpom</div>
          <div class="flex bg-base-200">nickname: dream</div>
          <div class="flex bg-base-200">ID studen : 6314110014</div>
          <div class="flex bg-base-200">age : 21</div>
          <div class="flex bg-base-200">sex : male</div>
          <div class="flex bg-base-200">height : 180</div>
          <div class="flex bg-base-200">weight : 70</div>
          <div class="flex bg-base-200">tell : 0917308573</div>
          <div class="flex bg-base-200">email : baju.bj04@gmail.com</div>
          <div class="flex bg-base-200">hobby : listen to music</div>
          <div class="flex bg-base-200">Color fav: Blue</div>
          <div class="flex bg-base-200"></div>
          <div class="flex bg-base-200"></div>
        </div>
      </div>
    </div>

   <div class="section" data-theme="aqua">
    <div class="flex h-screen">
      <div class="m-auto">
        <h3>section two</h3>
      </div>
    </div>
  </div> 
  <div class="section" data-theme="halloween">
    <div class="flex h-screen">
      <div class="m-auto">
        <h3>section three</h3>
      </div>
    </div>
  </div> 
</template> -->

<!-- <template>
   <div class="overflow-x-auto">
    <table class="table">
      head
      <thead>
        <tr>
          <th></th>
          <th>NO.</th>
          <th>Name</th>
          <th>Price</th>
        </tr>
      </thead>
      <tbody>

        <tr>
          <th></th>
          <td>1 <br>2 <br> 3 <br> 4 <br>5 <br>6 <br>7 <br> 8 <br> 9 <br> 10</td>

          <td>
            <div v-for="product in products" :key="product._id">
              {{ product.name }}
            </div>
          </td>
          <div v-for="product in products" :key="product._id">
              {{ product.price }}
            </div>
        </tr>

      </tbody>
    </table>
  </div>
  
</template>

<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue';
let products = ref()
onMounted(async () => {
  products.value = await getAllProduct();
  console.log(products);
})

const getAllProduct = async () => {
  let data = [];
  data = await axios.get('http://localhost:5000/getallproduct').then((response) => {
    return response.data;
  });
  return data;
}

</script>

<style scoped></style> -->

<template>
  <header>
    <div class="navbar bg-base-100">
      <div class="navbar-start">
        <div class="dropdown">
          <label tabindex="0" class="btn btn-ghost lg:hidden">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" /></svg>
          </label>
          <ul tabindex="0" class="menu menu-sm dropdown-content mt-3 z-[1] p-2 shadow bg-base-100 rounded-box w-52">
            <li v-for="menu in menuList" :key="menu.name"><RouterLink :to="menu.path">{{ menu.name }}</RouterLink></li>
          </ul>
        </div>
        <a class="btn btn-ghost normal-case text-xl">daisyUI</a>
      </div>
      <div class="navbar-center hidden lg:flex">
        <ul class="menu menu-horizontal px-1">
          <li v-for="menu in menuList" :key="menu.name"><RouterLink :to="menu.path">{{ menu.name }}</RouterLink></li>
        </ul>
      </div>
      <!-- <div class="navbar-end">
        <a class="btn">Button</a>
      </div> -->
    </div>
  </header>
  <div class="container mx-auto">
    <RouterView :key="router.currentRoute.value.name"/>
    <!-- <RouterView></RouterView> -->
  </div>
</template>

<script setup>
import { RouterView, RouterLink } from 'vue-router';
import router from './router';
const menuList = [
  { path:"/", name: "home"},
  { path:"/create", name: "Create"}
]

</script>

<style scoped>

</style>