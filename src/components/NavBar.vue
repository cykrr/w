<template>
<div id = "nav-bar">
  <div id = "sandwich">
    <svg id = "hamburger" viewBox="0 0 30 30">
      <rect y = "3" width="30" height="4"></rect>
      <rect y="13" width="30" height="4"></rect>
      <rect y="23" width="30" height="4"></rect>
    </svg>
  </div>
</div>
</template>
<script>
export default {

}
</script>

<style scoped>

#nav-bar {
    width: 100%;
    height: 50px;
    background-color: #eeeeee;
    margin-bottom: 30px;
    overflow: hidden;
    position: fixed;
    top: 0px;
    z-index: 1;
}

#sandwich {
  height: 50px;
  width: 50px;
  padding: 10px;
  transition: background-color 0.5s;
  cursor: pointer;
}

#sandwich:hover {
  background-color: #aaaaaa;
}

@media (min-width: 1024px) {
#nav-bar {
  top: 20px;
  border-radius: 50px;
  width: 96vw;
  left: 2vw;
  filter: drop-shadow(5px 5px 10px #707070);
  }
#sandwich {
  border-radius: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  }
#sandwich:hover {
  border-radius: 50px;
  }
#hamburger {
    width: 20px;
    height: 20px;
  }

}

</style>
