<template>
  <div id="content">
    <div class="teaser">
      <div class="teaser-content">
        Galeri Wisata.
      </div>
    </div>
    
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.teaser {
  position: relative;
  width: 100%;
  max-width: calc(100% - 10px);
  height: 350px;
  margin-bottom: 40px;
  background-image: url("../assets/pasarterapung2.jpg");
  background-size: cover;
  background-position: top;
  border-radius: 20px;
box-shadow: inset 1px 2000px rgba(0, 0, 0, 0.54);

}
  .teaser-content {
    position: absolute;
font-weight: bold;
    padding: 0 0 0 20px;
    opacity: 100%;
    color: #efefef;
    font-size: 3em;
        margin: 0;
    top: 50%;
    text-decoration:overline;
    z-index: 10;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, -50%) 
      }
</style>