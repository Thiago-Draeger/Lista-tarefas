<template>
  <header>
    <h1> {{valor}} </h1>
  </header>
</template>

<script>
export default {
  props: ["valor"],
};
</script>

<style scope>
header {
  background-color:purple;
  height: 50px;
  width: 100%;
  position: static;
}

header h1 {
  margin: 0px;
  color: whitesmoke;
  text-align: center;
  padding: 5px;
  font-size: 30px;
}

</style>