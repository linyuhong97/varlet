# 加载

### 引入

```js
import { createApp } from 'vue'
import { Loading } from '@varlet/ui'

createApp().use(Loading)
```

### Loading 类型

```html
<var-loading type="circle" />
<var-loading type="cube" />
<var-loading type="wave" />
<var-loading type="rect" />
<var-loading type="disappear" />
```

### Loading 颜色
```html
<var-loading type="circle" color="#2979ff" />
<var-loading type="cube" color="#2979ff" />
<var-loading type="wave" color="#2979ff" />
<var-loading type="rect" color="#2979ff" />
<var-loading type="disappear" color="#2979ff" />
```

### Loading 大小

```html
<var-loading type="circle" size="small" />
<var-loading type="cube" size="small" />
<var-loading type="wave" size="small" />
<var-loading type="rect" size="small" />
<var-loading type="disappear" size="small" />
```

### 包裹内容

```html
<var-button @click="loading = !loading" style="margin-bottom: 8px">
  {{ loading ? '关闭' : '打开' }}
</var-button>
<var-loading description="loading...." type="circle" :loading="loading">
  <var-card title="介绍" description="Varlet 是一个基于Vue3开发的 Material 风格移动端组件库，全面拥抱Vue3生态，由社区的小伙伴开发和维护。" />
</var-loading>
```

```javascript
import { ref } from 'vue'

export default {
  setup() {
    const loading = ref(false)

    return {
      loading,
    }
  }
}
```

## API

### 属性

| 参数     | 说明                                                              | 类型     | 默认值          |
| -------- | ---------------------------------------------------------------- | -------- | -------------- |
| `color`  | loading 的颜色                                                    | _string_ | `currentColor` |
| `type`   | loading 的类型，可选值为 `circle` `wave` `cube` `rect` `disappear` | _string_ | `circle`       |
| `size`   | loading 的大小，可选值位 `large` `normal` `small` `mini`           | _string_ | `normal`       |
| `description`   | loading 的描述文字                                          | _string_ | `-`            |
| `loading`| 存在内容时 loading 是否显示                                         | _boolean_ | `false`      |
| `radius` | loading 的类型为 `circle` 时，可设置其大小                          | _string \| number_  | `-` |

### 插槽

| 插槽名 | 说明 | 参数 |
| --- | --- | --- |
| `default` | `loading` 包裹着的内容 | `-` |
| `description`    | `loading` 的描述文字 | `-` |

### 样式变量
以下为组件使用的css变量,可以使用[StyleProvider组件](#/zh-CN/style-provider)进行样式定制

| 变量名 | 默认值 |
| --- | --- |
| `--loading-opacity` | `0.38` |
| `--loading-desc-margin` | `8px 0 0` |
