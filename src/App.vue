<template>
  <router-view/>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@200;300;400;600;700;800;900&display=swap');
$mainBackground: #e1e5ea;
$cardBackground: #faf3f3;
$headerColor: #a7bbc7;
$elementColor: #da7f8f;
$white: #ffffff;
$textColor: #2c3e50;
* {
  margin: 0;
  padding: 0;
  font-family: 'Nunito', sans-serif;
}
::-webkit-scrollbar {
  width: 0px;
}
body {
  background-color: $mainBackground;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $textColor;
}
</style>
