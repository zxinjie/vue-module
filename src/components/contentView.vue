<template>
  <div class="content-body">
    <div class="title-style">title</div>
    <div class="content-style">content</div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>

.content-body {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    position: relative;
}

.title-style {
    height: 32px;
    width: 100%;
    display: flex;
    align-items: center;
    text-align: center;
    justify-content: center
}

.content-style {
    width: 100%;
    max-height: 80vw;
}
</style>