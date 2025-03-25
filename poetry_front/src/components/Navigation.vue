<template>
    <div class="navbar">
      <ul>
        <li><router-link to="/recommend">诗词推荐</router-link></li>
        <li><router-link to="/search">诗词搜索</router-link></li>
        <li><router-link to="/game">诗词测验</router-link></li>
        <li><router-link to="/feihua">飞花令</router-link></li>
        <li><router-link to="/forum">交流论坛</router-link></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Navigation'
  }
  </script>