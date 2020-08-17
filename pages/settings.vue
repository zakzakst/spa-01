<template>
  <div>
    <h1 class="title">設定</h1>
    <div>
      <div class="field is-horizontal">
        <div class="field-label">
          <label class="label has-text-left">テーマ</label>
        </div>
        <div class="field-body">
          <div class="field is-narrow">
            <div class="control">
              <label v-for="theme in themeItems" :key="theme.value" class="radio">
                <input type="radio" v-model="inputTheme" :value="theme.value">
                {{ theme.label }}
              </label>
            </div>
          </div>
        </div>
      </div>
      <div class="field is-horizontal">
        <div class="field-label is-normal">
          <label class="label has-text-left">フォントサイズ</label>
        </div>
        <div class="field-body">
          <div class="field">
            <div class="control">
              <input class="input" type="number" v-model="inputFontSize">
            </div>
          </div>
        </div>
      </div>
      <div class="field is-horizontal">
        <div class="field-label has-text-left"></div>
        <div class="field-body">
          <div class="field">
            <div class="control">
              <button class="button is-primary" @click="updateSettings">設定更新</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      themeItems: [
        {
          label: '青',
          value: 'blue'
        },
        {
          label: '緑',
          value: 'green'
        },
        {
          label: '赤',
          value: 'red'
        },
        {
          label: '黄',
          value: 'yellow'
        },
      ],
      inputTheme: '',
      inputFontSize: 14,
    }
  },
  methods: {
    updateSettings() {
      console.log('更新');
    },
  }
}
</script>
