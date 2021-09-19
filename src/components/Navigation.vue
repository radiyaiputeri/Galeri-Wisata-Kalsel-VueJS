<template>
  <div id="navigation">
    <ul>
      <li>Kalimantan Selatan</li>
    

    </ul>
    <div class="search">
      <input type="text" placeholder="Search for articles, people or magazines" />
      <i class="fas fa-search"></i>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
#navigation {
  display: flex;
  width: 100%;
  margin-bottom: 20px;
  ul {
    display: flex;
    list-style: none;
    padding: 0;
    margin: 0 20px 0 0;
    li {
      font-size: 1.5rem;
      padding: 2px 10px;
      cursor: pointer;
      &:hover {
        color: #fdfdfd;
      }
    }
  }
  .search {
    position: relative;
    
    width: 100%;
    input {
      border: none;
      outline: none;
      width: calc(100% - 100px);
      padding: 15px 60px 15px 20px;
      margin: 0;
      border-radius: 20px;
      background-color: #ecaa37;
      font-family: "Segoe UI", Tahoma;
      font-size: 1rem;
    }
    i {
      position: absolute;
      right: 20px;
      top: 15px;
      font-size: 1.6rem;
      color: #aaa;
      cursor: pointer;
    }
  }
}
</style>