 <template>
  <h1>{{title}}</h1>
  <p>Welcome.....</p>
<teleport to=".modals" v-if="showModal">
  <Modal  theme="sale" @close="toggleModal">
    <template v-slot:links>
      <a href="#">sign up now</a>

      <a href="#">more info</a>
    </template>

    <h1>Ninja Giveaway!</h1>
    <p>Grab your ninja swag for half price!</p>

  </Modal>

</teleport>
   <teleport  to=".modals" v-if="showModalTwo">
     <Modal   @close="toggleModalTwo">
       <h1>NewsLetter</h1>
       <p>Updates!</p>
     </Modal>
   </teleport>
   <button @click="toggleModal"> open modal</button>
   <button @click="toggleModalTwo">modal two</button>
</template>


<script>
import Modal from './components/Modal'


export default {
  name: 'App',
  components : {Modal},
  data(){
    return{
      title: 'My first Vue App :)',
      showModal: false,
      showModalTwo:false
    }
  },
  methods:{
    toggleModal(){
      this.showModal=!this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo=!this.showModalTwo
    }
  }
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
