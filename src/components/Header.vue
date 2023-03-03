<template>
    <header class="main-header">
      <div class="container">
        <h1>{{ title }}</h1>
      </div>
  
    </header>
  </template>
  
  <script>
    export default {
      data() {
        return {
          title: 'Yu-Gi-Oh Api'
        }
      }
      
    }
  </script>
  
  <style lang="scss" scoped>
  .main-header {
    text-align: center;
    font-size: 2rem;
    padding: 1rem 0;
  }
  </style>