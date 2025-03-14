# v-confetti

## 功能

点击元素触发全屏五彩纸屑动画效果，适用于表单提交成功等场景

## 参数

- `count`: 粒子数量（默认：50）
- `colors`: 颜色数组（默认：彩虹七色）

## 使用示例

```vue
<template>
  <button v-confetti>提交</button>
  <button v-confetti="{ count: 100, colors: ['#ff0000', '#00ff00'] }">定制效果</button>
</template>
```

## 基础用法

通告给目标点击元素添加`v-confetti`指令，点击后会触发全屏五彩纸屑动画效果

<Demo />

::: details 查看代码
<<< @/.vitepress/components/vConfetti/Demo.vue

:::

## 高级用法

可以通过`count`和`colors`参数来定制五彩纸屑动画效果
<CountAndColors />
::: details 查看代码
<<< @/.vitepress/components/vConfetti/CountAndColors.vue
:::

## API

<ApiTable :data="props" />

## 注意事项

- 会自动添加pointer-events: none防止点击干扰
- 动画结束后会自动移除canvas元素
- 建议在按钮点击事件处理完成后触发

<script setup>
  import Demo from "../.vitepress/components/vConfetti/Demo.vue"
  import CountAndColors from "../.vitepress/components/vConfetti/CountAndColors.vue"
  import ApiTable from "../.vitepress/components/ApiTable.vue"

  const props = [
    {
      name: 'count',
      type: 'number',
      default: '200',
      description: '屏幕中最大展示的纸屑数量，超出的部分会被自动裁剪，当然不是越多越好，会影响性能',
      required: false
    },
    {
      name: 'colors',
      type: 'string[]',
      default: '彩虹七色',
      description: '颜色数组，可以是十六进制颜色值，也可以是rgb或rgba颜色值，',
      required: false
    }
  ]
</script>
