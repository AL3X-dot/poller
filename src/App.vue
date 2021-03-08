<template>
  <nav class="nav-wrapper grey lighten-3 z-depth-2 valign-wrapper">
    <div class="brand-logo black-text center ">
      <span><i class="material-icons" id="logo">done_all</i>Pollitout</span>
    </div>
  </nav>
  <div class="container">
    <div class="row">
      <div class="col l8 offset-l2 m8 offset-m2 s12">
        <div class="card">
          <div class="card-image">
            <img src="./assets/anonymous.jpg" alt="anonymous" class="responsive-img">
            <span class="card-title left">You are Anonymous</span>
          </div>
          <div class="card-action">
            <div class="row center">
              <a class="blue-text text-darken-1 activator" @click="create">Create A Poll</a>
            </div>
            <div class="row center" style="margin-bottom:0">
              <a class="blue-text text-darken-1 activator" @click='join'>Join A Poll</a>
            </div>
          </div>
          <div :class='c_c_class' :style="hide" id="create">
            <span class="card-title grey-text text-darken-4">Create<i class="material-icons right">close</i></span>
            <div class="row center input-field valign-wrapper">
              <div class="col s10 input-field">
                <label for="">Enter new options</label>
                <input type="text" v-model="option">
              </div>
              <div class="col s2">
                <i class="material-icons" style="cursor:pointer" @click='addOption'>add</i>
              </div>
            </div>
            <div class="row">
              <blockquote class="flow-text" v-for='(option,index) in options' :key='index' id="options">
                {{option}}
                <i class="material-icons right">delete</i>
              </blockquote>
            </div>
          </div>
          <div :class="j_c_class" :style="hide" id="join">
            <span class="card-title grey-text text-darken-4">Join<i class="material-icons right">close</i></span>
            <p>Lorem ipsum dolor sit amet.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      c_c_class:'',
      show:'display:',
      j_c_class:'',
      hide:"display:none",
      option:'',
      options:[]
    }
  },
  created(){
  },
  methods:{
    create(){
      this.j_c_class=''
      this.c_c_class='card-reveal'
      this.c_c_display=''
    },
    join(){
      this.c_c_class=''
      this.j_c_class='card-reveal'
      this.j_c_display=''
    },
    addOption(){
      this.options.push(this.option)
    }
  }
}
</script>

<style>
  #logo{
    margin-top:5px
  }
  .myTitle{
    font-weight: 400;
  }
  #options:hover{
    box-shadow:10px 10px 20px grey
  }
</style>
