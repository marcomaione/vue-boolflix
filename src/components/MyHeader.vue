<template>
  <div class="up">
      <h1>BOOLFLIX</h1>
      <div class="cerca">
          <input type="text">
          <button>cerca</button>
      </div>

  </div>
</template>

<script>
export default {
    name:"MyHeader",

}
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.up {
    background-color:black ;
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    h1 {
        color: red;
        margin-left: 20px;
    }
    .cerca {
        margin-right: 20px;
    }
}
</style>