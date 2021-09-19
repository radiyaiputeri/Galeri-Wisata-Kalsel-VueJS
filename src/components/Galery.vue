<template>
    <v-container>
       <v-row>
        <v-col v-for="item in items" :key="item.id" class="d-flex child-flex" cols="6" sm="4">
          <v-card flat tile class="d-flex">
            <v-img :src="item.src" aspect-ratio="1" id="gambar" @click="imgClick(item)">
            </v-img>
          </v-card>
          <transition name="fade" appear>
           <transition name="slide" appear>
                <div class="modal-overlay" v-if="item.show" @click="item.show = false"> 
                  <div class="modalbox">
                     <v-img :src="item.src" aspect-ratio="1" class="modalimg">
                     <button class="close" @click="item.show=false"> 
                    <i class="fas fa-times fa-1x" ></i>
                    </button>
                     </v-img>
                     <div class="judul">{{item.nama}}</div>
                      </div>
                </div>
            </transition>
            </transition>
        </v-col>
      </v-row>
    </v-container>
</template>


<script>
export default {
    name: "Galery",

    data() {
      return {

       images: {},
       items: [
        {
          id: 1,
          src: require("../assets/images/img1.jpg"),
          nama: "Air Terjun Panayar"

        },
        {
          id: 2,
          src: require("../assets/images/img2.jpg"),
          nama: "Danau Biru Pengaron"
        },
        {
          id: 3,
          src: require("../assets/images/img3.jpg"),
          nama: "Danau Unes 121"
        },
        {
          id: 4,
          src: require("../assets/images/img4.jpg"),
          nama: "Gunung Rimpi"
        },
        {
          id: 5,
          src: require("../assets/images/img5.jpg"),
          nama: "Jembatan Barito"
        },
        {
          id: 6,
          src: require("../assets/images/img6.jpg"),
          nama:"Menara Pandang"
        },
        {
          id: 7,
          src: require("../assets/images/img7.jpg"),
          nama: "Pantai Angsana"
        },
        {
          id: 8,
          src: require("../assets/images/img8.jpg"),
          nama: "Pantai Joras"
        },
        {
          id: 9,
          src: require("../assets/images/img9.jpg"),
          nama: "Pantai Tamiang"
        }
      ]
    };
  }
 ,
 created(){
   this.items= this.items.map(item => {
     return{...item, show: false}
   })
 },
 methods:{
    imgClick(item){
      item.show= true;
    },

 }

};
</script>
<style lang="scss" scoped>
#gambar{
  cursor:pointer;
  transition: 0.4s ease-out;

background-color: rgb(20, 19, 19);

  &:hover{
    box-shadow: 6px 6px rgba(245, 155, 19, 0.836);
    opacity: 70%;
  }
}

.modal-overlay {
  background-color: rgba(0,0,0,0.5);
  background-opacity: 50%;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 1050;
  padding: 50px;
}

.fade-enter-active, .fade-leave-active{
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to{
  opacity: 0;
}

.modalimg{
 
  border-top-left-radius: 30px;
  border-top-right-radius: 30px;

  
}
.modalbox{
  position: fixed;
  top: 50%;
  left:50%;
  transform: translate(-50%,-50%);
  z-index: 1050;
  width: 100%;
  height: auto;
  
  max-width: 480px;
  background-color: #FF8C00;
  border-radius: 30px;

}
.judul{
  padding: 10px;
  top: 50px;
    text-align: center;

      font-size: 1.5rem;
    
}

.close{
       position: fixed;
     top: 20px;
     right:20px;
      font-size: 1.6rem;
      color: #FF8C00;
      cursor: pointer;
      i{
        color:#FF8C00;
      }
}

</style>