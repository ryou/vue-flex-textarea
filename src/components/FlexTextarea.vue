<template>
  <div class="c-flexTextarea">
    <div class="dummy" aria-hidden="true">{{ dummyText }}</div>
    <textarea :value="value" @input="onInput" />
  </div>
</template>

<script>
const ZERO_WIDTH_SPACE = "\u200b";

export default {
  name: "FlexTextarea",
  props: {
    value: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      dummyText: ""
    };
  },
  methods: {
    onInput(e) {
      const newValue = e.target.value;
      this.dummyText = newValue + ZERO_WIDTH_SPACE;
      this.$emit("input", newValue);
    }
  }
};
</script>

<style lang="scss" scoped>
@mixin commonStyle {
  width: 100%;
  font: inherit;
  color: inherit;
  letter-spacing: inherit;
  padding: 5px 15px;
  margin: 0;
  box-sizing: border-box;
  border: 1px solid #aaa;
  border-radius: 5px;
}

.c-flexTextarea {
  position: relative;
  font-size: 16px;
  line-height: 1.8;
  text-align: left;
}
.dummy {
  white-space: pre-wrap;
  word-wrap: break-word;
  overflow-wrap: break-word;
  min-height: 120px;
  @include commonStyle;
}
textarea {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  resize: none;
  @include commonStyle;
}
</style>
