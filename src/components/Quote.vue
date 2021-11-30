<template>
  <div class="col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <i class=" icon fas fa-times"></i>
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style>
.panel-body {
  font-family: 'Arizonia', cursive;
  font-size: 24px;
  color: #6e6e6e;
  position: relative;
}
.panel-body:hover .icon {
    display: inline-block;
}
.quote {
  cursor: pointer;
 
}
.quote:hover {
  background-color: #ffe2e2;
}
.icon {
  display: none;
  position: absolute;
  font-size: 16px;
  top: 1%;
  right: 2%;
} 
</style>