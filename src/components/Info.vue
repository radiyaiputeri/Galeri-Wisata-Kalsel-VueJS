<template>
    <div class="infonote">
      <div class="infobox">
        <div class="title">Articles</div>
        <div class="value">128</div>
      </div>
      <div class="infobox">
        <div class="title">Readers</div>
        <div class="value">18k</div>
      </div>
      <div class="infobox">
        <div class="title">Likes</div>
        <div class="value">302k</div>
      </div>
      <div class="infobox">
        <div class="title">Comments</div>
        <div class="value">145k</div>
      </div>
    </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.infonote {
  position: relative;
  width: 100%;
  max-width: calc(100% - 10px);
  height: 90px;
  margin-bottom: 40px;
  overflow: hidden;

  .infobox {
    float: left;
    width: 120px;
    height: 90px;
    padding: 10px;
    margin: 0 20px 20px 0;
    border-radius: 20px;
    border: 2px solid #ccc;
    .title {
      font-weight: bold;
    }
    .value {
      padding: 10px 0 0 0;
      font-size: 2rem;
    }
  }
}
</style>