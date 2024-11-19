<template>
  <div>
    這是一個卡片元件
    <br />
    <br />
    <br />
    <br />
    {{ text }}
    <br />
    <br />
    <br />
    <br />
    {{data}}
    <br />
    <br />
    <br />
    <br />
    {{envir}}
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "一段文字",
      data: {},
      envir:"",
    };
  },

  mounted() {
    const url = import.meta.env.VITE_PATH;
    this.envir = import.meta.env.VITE_TEXT;
    this.$http.get(url).then((res) => {
        this.data = res.data.results[0];
    })
  },
};
</script>