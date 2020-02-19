<template>
  <label class="switch" :yearly="recurring">
  <input type="checkbox" @change="alertme()" checked='true'>
  <span class="slider round"></span>
</label>
</template>

<script>
export default {
  props:['yearly'],
  data(){
    return{
      recurring: true
    }
  },
  methods:{
    alertme(){
      this.recurring = !this.recurring;
      this.$emit('update:recurring', this.recurring)
    }
  }
}
</script>

<style>
/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  box-shadow: inset 2px 2px 6px #adadad, 
            inset -2px -2px 6px #ebebeb;
  -webkit-transition: .4s;
  transition: .4s;
}
.slider:focus{
  outline: none;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background: linear-gradient(145deg, #e6e6e6, #ffffff);
box-shadow:  2px 2px 6px #d9d9d9, 
             -2px -2px 60px #ffffff;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background: #548C86;
box-shadow: inset 2px 2px 6px #477772, 
            inset -2px -2px 6px #61a19a;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
  outline: none;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

</style>