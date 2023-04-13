<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <div class="card mt-2">
          <div class="card-header">
            <h2>Odontograma</h2>
          </div>
          <div class="card-body table-responsive">
            <table class="table">
              <thead>
                <tr>
                  <th scope="col" class="text-center">18</th>
                  <th scope="col" class="text-center">17</th>
                  <th scope="col" class="text-center">16</th>
                  <th scope="col" class="text-center">15</th>
                  <th scope="col" class="text-center">14</th>
                  <th scope="col" class="text-center">13</th>
                  <th scope="col" class="text-center">12</th>
                  <th scope="col" class="text-center">11</th>

                  <th scope="col" class="text-center"></th>
                  
                  <th scope="col" class="text-center">21</th>
                  <th scope="col" class="text-center">22</th>
                  <th scope="col" class="text-center">23</th>
                  <th scope="col" class="text-center">24</th>
                  <th scope="col" class="text-center">25</th>
                  <th scope="col" class="text-center">26</th>
                  <th scope="col" class="text-center">27</th>
                  <th scope="col" class="text-center">28</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td v-for="(item, key) in teeth[0]" :key="key" class="text-center" @click="teethSelected = item">
                    <img :src="item.img" width="60" alt="">
                  </td>

                  <td class="text-center"></td>

                  <td v-for="(item, key) in teeth[1]" :key="key" class="text-center" @click="teethSelected = item">
                    <img :src="item.img" width="60" alt="">
                  </td>
                
                </tr>

                <tr>
                  <td v-for="(item, key) in teeth[2]" :key="key" class="text-center" @click="teethSelected = item">
                    <img :src="item.img" width="60" alt="">
                  </td>

                  <td class="text-center"></td>

                  <td v-for="(item, key) in teeth[3]" :key="key" class="text-center" @click="teethSelected = item">
                    <img :src="item.img" width="60" alt="">
                  </td>
                </tr>
              </tbody>
              <tfoot>
                <tr>
                  <th scope="col" class="text-center">48</th>
                  <th scope="col" class="text-center">47</th>
                  <th scope="col" class="text-center">46</th>
                  <th scope="col" class="text-center">45</th>
                  <th scope="col" class="text-center">44</th>
                  <th scope="col" class="text-center">43</th>
                  <th scope="col" class="text-center">42</th>
                  <th scope="col" class="text-center">41</th>

                  <th scope="col" class="text-center"></th>
                  
                  <th scope="col" class="text-center">31</th>
                  <th scope="col" class="text-center">32</th>
                  <th scope="col" class="text-center">33</th>
                  <th scope="col" class="text-center">34</th>
                  <th scope="col" class="text-center">35</th>
                  <th scope="col" class="text-center">36</th>
                  <th scope="col" class="text-center">37</th>
                  <th scope="col" class="text-center">38</th>
                </tr>
              </tfoot>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default{
    name: 'OdontogramaHome',
    setup(){
      let teeth = ref([
        [
          {id: 18 , img:'/assets/img/teeth/11-18/18/18.png'},
          {id: 17 , img:'/assets/img/teeth/11-18/17/17.png'},
          {id: 16 , img:'/assets/img/teeth/11-18/16/16.png'},
          {id: 15 , img:'/assets/img/teeth/11-18/15/15.png'},
          {id: 14 , img:'/assets/img/teeth/11-18/14/14.png'},
          {id: 13 , img:'/assets/img/teeth/11-18/13/13.png'},
          {id: 12 , img:'/assets/img/teeth/11-18/12/12.png'},
          {id: 12 , img:'/assets/img/teeth/11-18/11/11.png'},
        ],
        [
          {id: 21 , img:'/assets/img/teeth/21-28/21/21.png'},
          {id: 22 , img:'/assets/img/teeth/21-28/22/22.png'},
          {id: 23 , img:'/assets/img/teeth/21-28/23/23.png'},
          {id: 24 , img:'/assets/img/teeth/21-28/24/24.png'},
          {id: 25 , img:'/assets/img/teeth/21-28/25/25.png'},
          {id: 26 , img:'/assets/img/teeth/21-28/26/26.png'},
          {id: 27 , img:'/assets/img/teeth/21-28/27/27.png'},
          {id: 28 , img:'/assets/img/teeth/21-28/28/28.png'},
        ],
        [
          {id: 48 , img:'/assets/img/teeth/41-48/48/48.png'},
          {id: 47 , img:'/assets/img/teeth/41-48/47/47.png'},
          {id: 46 , img:'/assets/img/teeth/41-48/46/46.png'},
          {id: 45 , img:'/assets/img/teeth/41-48/45/45.png'},
          {id: 44 , img:'/assets/img/teeth/41-48/44/44.png'},
          {id: 43 , img:'/assets/img/teeth/41-48/43/43.png'},
          {id: 42 , img:'/assets/img/teeth/41-48/42/42.png'},
          {id: 42 , img:'/assets/img/teeth/41-48/41/41.png'},
        ],
        [
          {id: 31 , img:'/assets/img/teeth/31-38/31/31.png'},
          {id: 32 , img:'/assets/img/teeth/31-38/32/32.png'},
          {id: 33 , img:'/assets/img/teeth/31-38/33/33.png'},
          {id: 34 , img:'/assets/img/teeth/31-38/34/34.png'},
          {id: 35 , img:'/assets/img/teeth/31-38/35/35.png'},
          {id: 36 , img:'/assets/img/teeth/31-38/36/36.png'},
          {id: 37 , img:'/assets/img/teeth/31-38/37/37.png'},
          {id: 38 , img:'/assets/img/teeth/31-38/38/38.png'},
        ],
        
      ]);

      let teethSelected = ref([]);

      return {
        teeth,teethSelected
      }
    }
  }
</script>