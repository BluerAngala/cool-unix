# Cool Unix 组件库使用说明

## 📖 简介

Cool Unix 是一个基于 uni-app x 的跨端应用开发脚手架，内置了功能丰富的 **Cool UI** 组件库。该组件库提供了大量开箱即用的 UI 组件，支持 PassThrough 样式定制、TailwindCSS 深度集成，以及完善的类型定义，极大提升了开发效率。

## 🚀 快速开始

### 安装

Cool UI 组件库已内置在 Cool Unix 脚手架中，无需额外安装。

### 基础使用

在页面中直接引入组件即可使用：

```uvue
<template>
  <cl-page>
    <view class="p-3">
      <cl-button type="primary">点击按钮</cl-button>
    </view>
  </cl-page>
</template>

<script lang="ts" setup>
// 无需导入，组件已全局注册
</script>
```

## 📦 组件分类

### 基础组件

#### cl-text - 文本组件
用于显示文本内容，支持多种样式定制。

```uvue
<cl-text>普通文本</cl-text>
<cl-text type="primary">主要文本</cl-text>
<cl-text type="success">成功文本</cl-text>
<cl-text type="warn">警告文本</cl-text>
<cl-text type="error">错误文本</cl-text>
```

#### cl-button - 按钮组件
功能丰富的按钮组件，支持多种类型、尺寸和状态。

```uvue
<!-- 基础用法 -->
<cl-button>普通按钮</cl-button>

<!-- 不同类型 -->
<cl-button type="primary">主要按钮</cl-button>
<cl-button type="success">成功按钮</cl-button>
<cl-button type="warn">警告按钮</cl-button>
<cl-button type="error">危险按钮</cl-button>
<cl-button type="info">信息按钮</cl-button>

<!-- 不同尺寸 -->
<cl-button size="small">小按钮</cl-button>
<cl-button size="normal">默认按钮</cl-button>
<cl-button size="large">大按钮</cl-button>

<!-- 带图标 -->
<cl-button type="primary" icon="send-plane-fill">发送</cl-button>

<!-- 加载状态 -->
<cl-button type="primary" :loading="true">加载中</cl-button>

<!-- 禁用状态 -->
<cl-button type="primary" :disabled="true">已禁用</cl-button>
```

#### cl-icon - 图标组件
用于显示图标，支持多种图标库。

```uvue
<cl-icon name="home-line"></cl-icon>
<cl-icon name="user-fill" :size="30" color="#4286e0"></cl-icon>
```

#### cl-image - 图片组件
增强的图片组件，支持懒加载、占位图等功能。

```uvue
<cl-image src="/static/logo.png"></cl-image>
<cl-image src="/static/logo.png" mode="aspectFit" :lazy-load="true"></cl-image>
```

#### cl-tag - 标签组件
用于标记和分类的标签组件。

```uvue
<cl-tag>标签</cl-tag>
<cl-tag type="primary">主要标签</cl-tag>
<cl-tag type="success">成功标签</cl-tag>
<cl-tag type="warn">警告标签</cl-tag>
<cl-tag type="error">错误标签</cl-tag>
```

### 表单组件

#### cl-input - 输入框组件
功能完整的输入框组件，支持多种输入类型。

```uvue
<!-- 基础用法 -->
<cl-input v-model="value"></cl-input>

<!-- 数字输入 -->
<cl-input type="number" v-model="number"></cl-input>

<!-- 密码输入 -->
<cl-input password v-model="password"></cl-input>

<!-- 可清除 -->
<cl-input clearable v-model="text"></cl-input>

<!-- 带图标 -->
<cl-input prefix-icon="search-line" v-model="search"></cl-input>
<cl-input suffix-icon="text" v-model="text"></cl-input>

<!-- 左右插槽 -->
<cl-input v-model="text">
  <template #prepend>
    <cl-button type="primary" size="small" icon="search-line"></cl-button>
  </template>
  <template #append>
    <cl-button type="primary" size="small" icon="send-plane-fill"></cl-button>
  </template>
</cl-input>
```

#### cl-textarea - 文本域组件
多行文本输入组件。

```uvue
<cl-textarea v-model="content" :maxlength="200"></cl-textarea>
```

#### cl-input-number - 计数器组件
数字输入计数器，支持增减操作。

```uvue
<cl-input-number v-model="count" :min="0" :max="100" :step="1"></cl-input-number>
```

#### cl-input-otp - 口令输入组件
用于验证码、密码等场景的口令输入框。

```uvue
<cl-input-otp v-model="otp" :length="6"></cl-input-otp>
```

#### cl-checkbox - 多选框组件
多选复选框组件。

```uvue
<cl-checkbox v-model="checked">选项</cl-checkbox>

<!-- 复选框组 -->
<cl-checkbox-group v-model="checkedList">
  <cl-checkbox value="1">选项1</cl-checkbox>
  <cl-checkbox value="2">选项2</cl-checkbox>
  <cl-checkbox value="3">选项3</cl-checkbox>
</cl-checkbox-group>
```

#### cl-radio - 单选框组件
单选按钮组件。

```uvue
<cl-radio v-model="value" value="1">选项1</cl-radio>
<cl-radio v-model="value" value="2">选项2</cl-radio>

<!-- 单选框组 -->
<cl-radio-group v-model="selected">
  <cl-radio value="1">选项1</cl-radio>
  <cl-radio value="2">选项2</cl-radio>
  <cl-radio value="3">选项3</cl-radio>
</cl-radio-group>
```

#### cl-switch - 开关组件
开关切换组件。

```uvue
<cl-switch v-model="enabled"></cl-switch>
```

#### cl-slider - 滑块组件
数值选择滑块。

```uvue
<cl-slider v-model="value" :min="0" :max="100"></cl-slider>
```

#### cl-rate - 评分组件
星级评分组件。

```uvue
<cl-rate v-model="rating" :count="5"></cl-rate>
```

#### cl-select - 选择器组件
下拉选择组件。

```uvue
<cl-select v-model="selected" :options="options"></cl-select>
```

#### cl-calendar - 日历组件
日期选择日历。

```uvue
<cl-calendar v-model="date"></cl-calendar>
```

#### cl-cascader - 级联选择器
多级联动选择组件。

```uvue
<cl-cascader v-model="value" :options="cascaderOptions"></cl-cascader>
```

#### cl-upload - 上传组件
文件上传组件。

```uvue
<cl-upload
  v-model="fileList"
  :action="uploadUrl"
  :max-count="9"
></cl-upload>
```

#### cl-form - 表单组件
表单容器组件，支持表单验证。

```uvue
<cl-form ref="formRef" :model="form" :rules="rules">
  <cl-form-item label="用户名" prop="username">
    <cl-input v-model="form.username"></cl-input>
  </cl-form-item>
  <cl-form-item label="密码" prop="password">
    <cl-input password v-model="form.password"></cl-input>
  </cl-form-item>
  <cl-button type="primary" @tap="submit">提交</cl-button>
</cl-form>
```

### 布局组件

#### cl-page - 页面容器
页面根容器组件，自动处理滚动和样式。

```uvue
<template>
  <cl-page>
    <view class="p-3">
      <!-- 页面内容 -->
    </view>
  </cl-page>
</template>
```

#### cl-tabs - 标签页组件
标签页切换组件。

```uvue
<cl-tabs v-model="activeTab" :list="tabList"></cl-tabs>

<!-- 显示滑块 -->
<cl-tabs v-model="activeTab" :list="tabList" show-slider></cl-tabs>

<!-- 横向填充 -->
<cl-tabs v-model="activeTab" :list="tabList" fill></cl-tabs>
```

#### cl-collapse - 折叠面板
可折叠内容面板。

```uvue
<cl-collapse v-model="activeNames">
  <cl-collapse-item name="1" title="标题1">
    内容1
  </cl-collapse-item>
  <cl-collapse-item name="2" title="标题2">
    内容2
  </cl-collapse-item>
</cl-collapse>
```

#### cl-sticky - 吸顶组件
吸顶固定组件。

```uvue
<cl-sticky>
  <cl-button type="primary">吸顶按钮</cl-button>
</cl-sticky>
```

#### cl-footer - 底部操作栏
页面底部操作区域组件。

```uvue
<cl-page>
  <view class="p-3">
    <!-- 页面内容 -->
  </view>
  
  <cl-footer>
    <cl-button type="primary" fill>提交</cl-button>
  </cl-footer>
</cl-page>
```

#### cl-topbar - 顶部导航栏
自定义顶部导航栏。

```uvue
<cl-topbar title="页面标题"></cl-topbar>
```

#### cl-row / cl-col - 栅格布局
响应式栅格布局系统。

```uvue
<cl-row>
  <cl-col :span="8">列1</cl-col>
  <cl-col :span="8">列2</cl-col>
  <cl-col :span="8">列3</cl-col>
</cl-row>
```

### 数据展示组件

#### cl-list - 列表组件
列表容器组件。

```uvue
<cl-list border>
  <cl-list-item label="标题" value="内容"></cl-list-item>
  <cl-list-item label="标题" value="内容" arrow></cl-list-item>
</cl-list>
```

#### cl-list-view - 列表视图
高性能列表视图组件，支持虚拟滚动。

```uvue
<cl-list-view
  :data="list"
  :item-height="100"
  @load="onLoad"
>
  <template #default="{ item }">
    <view class="p-3">{{ item.name }}</view>
  </template>
</cl-list-view>
```

#### cl-waterfall - 瀑布流
瀑布流布局组件。

```uvue
<cl-waterfall :data="list" :column="2">
  <template #default="{ item }">
    <view>{{ item.name }}</view>
  </template>
</cl-waterfall>
```

#### cl-timeline - 时间轴
时间轴展示组件。

```uvue
<cl-timeline>
  <cl-timeline-item title="步骤1" content="内容1"></cl-timeline-item>
  <cl-timeline-item title="步骤2" content="内容2"></cl-timeline-item>
  <cl-timeline-item title="步骤3" content="内容3"></cl-timeline-item>
</cl-timeline>
```

#### cl-tree - 树形结构
树形数据展示组件。

```uvue
<cl-tree :data="treeData"></cl-tree>
```

#### cl-pagination - 分页组件
分页导航组件。

```uvue
<cl-pagination
  v-model="currentPage"
  :total="100"
  :page-size="10"
></cl-pagination>
```

#### cl-banner - 轮播图
轮播图组件。

```uvue
<cl-banner :list="bannerList" :height="200"></cl-banner>
```

#### cl-marquee - 跑马灯
文字滚动跑马灯组件。

```uvue
<cl-marquee :list="marqueeList"></cl-marquee>
```

### 反馈组件

#### cl-popup - 弹出层
弹出层组件，支持多种弹出方式。

```uvue
<cl-popup v-model="visible" direction="bottom">
  <view class="p-3">弹出内容</view>
</cl-popup>
```

#### cl-action-sheet - 操作菜单
底部操作菜单。

```uvue
<cl-action-sheet
  v-model="visible"
  :actions="actions"
  @select="onSelect"
></cl-action-sheet>
```

#### cl-toast - 提示框
轻提示组件。

```uvue
<script setup lang="ts">
import { useUi } from "@/uni_modules/cool-ui";

const ui = useUi();

function showToast() {
  ui.showToast({
    message: "操作成功"
  });
}
</script>
```

#### cl-confirm - 确认框
确认对话框。

```uvue
<script setup lang="ts">
import { useUi } from "@/uni_modules/cool-ui";

const ui = useUi();

function showConfirm() {
  ui.showConfirm({
    title: "提示",
    message: "确定要删除吗？",
    onConfirm: () => {
      // 确认操作
    }
  });
}
</script>
```

#### cl-loading - 加载中
加载指示器。

```uvue
<cl-loading :loading="isLoading"></cl-loading>
```

### 状态组件

#### cl-badge - 角标
角标组件，用于显示数字、红点等。

```uvue
<cl-badge :value="5">
  <cl-button>消息</cl-button>
</cl-badge>

<cl-badge dot>
  <cl-button>通知</cl-button>
</cl-badge>
```

#### cl-progress - 进度条
进度条组件。

```uvue
<cl-progress :percentage="50"></cl-progress>
<cl-progress :percentage="75" type="success"></cl-progress>
```

#### cl-progress-circle - 圆形进度条
圆形进度条组件。

```uvue
<cl-progress-circle :percentage="60" :size="100"></cl-progress-circle>
```

#### cl-skeleton - 骨架屏
骨架屏加载占位组件。

```uvue
<cl-skeleton :loading="loading" :rows="3"></cl-skeleton>
```

#### cl-loadmore - 加载更多
加载更多指示器。

```uvue
<cl-loadmore :status="status"></cl-loadmore>
```

#### cl-countdown - 倒计时
倒计时组件。

```uvue
<cl-countdown :time="60000" format="mm:ss"></cl-countdown>
```

#### cl-noticebar - 通知栏
顶部通知栏组件。

```uvue
<cl-noticebar text="这是一条通知消息"></cl-noticebar>
```

#### cl-rolling-number - 数字滚动
数字滚动动画组件。

```uvue
<cl-rolling-number :value="1234"></cl-rolling-number>
```

### 其他组件

#### cl-avatar - 头像
头像组件。

```uvue
<cl-avatar src="/static/avatar.png"></cl-avatar>
<cl-avatar name="张三"></cl-avatar>
```

#### cl-empty - 空状态
空状态占位组件。

```uvue
<cl-empty description="暂无数据"></cl-empty>
```

#### cl-qrcode - 二维码
二维码生成组件。

```uvue
<cl-qrcode value="https://example.com" :size="200"></cl-qrcode>
```

#### cl-cropper - 图片裁剪
图片裁剪组件。

```uvue
<cl-cropper
  :src="imageSrc"
  @confirm="onCrop"
></cl-cropper>
```

#### cl-draggable - 拖拽排序
拖拽排序组件。

```uvue
<cl-draggable v-model="list">
  <template #default="{ item }">
    <view>{{ item.name }}</view>
  </template>
</cl-draggable>
```

#### cl-filter-bar - 筛选栏
筛选栏组件。

```uvue
<cl-filter-bar :list="filterList" v-model="filterValue"></cl-filter-bar>
```

#### cl-float-view - 悬浮按钮
悬浮操作按钮。

```uvue
<cl-float-view position="bottom-right">
  <cl-button type="primary" icon="add-line"></cl-button>
</cl-float-view>
```

#### cl-back-top - 返回顶部
返回顶部按钮。

```uvue
<cl-back-top></cl-back-top>
```

#### cl-watermark - 水印
水印组件。

```uvue
<cl-watermark text="Cool Unix" :opacity="0.3"></cl-watermark>
```

#### cl-sign - 签名
签名画板组件。

```uvue
<cl-sign @confirm="onSignConfirm"></cl-sign>
```

#### cl-slide-verify - 滑动验证
滑动验证码组件。

```uvue
<cl-slide-verify @success="onVerifySuccess"></cl-slide-verify>
```

## 🎨 PassThrough (pt) 样式定制

PassThrough 是 Cool UI 组件库的核心特性，允许开发者通过 `pt` 属性直接访问组件内部的 DOM 结构，实现灵活的样式定制。

### 基础用法

```uvue
<cl-button
  :pt="{
    className: '!rounded-2xl'
  }"
>
  自定义按钮
</cl-button>
```

### 多层级定制

```uvue
<cl-button
  :pt="{
    className: '!rounded-2xl',
    icon: {
      size: 50,
      className: 'mr-5'
    },
    label: {
      color: 'red',
      className: 'font-bold'
    },
    loading: {
      size: 50
    }
  }"
>
  点击
</cl-button>
```

### 与 TailwindCSS 结合

```uvue
<cl-input
  :pt="{
    className: parseClass({
      '!bg-sky-100': isActive,
      '!border-sky-700': isActive
    }),
    inner: {
      className: parseClass({
        '!text-sky-700': isActive
      })
    }
  }"
></cl-input>
```

## 🎯 组件方法调用

使用 ref 调用组件内部方法时，需要注意类型定义：

```uvue
<template>
  <cl-popup ref="popupRef" v-model="visible">
    <view>内容</view>
  </cl-popup>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import type { ClPopupComponentPublicInstance } from "@/uni_modules/cool-ui";

const popupRef = ref<ClPopupComponentPublicInstance | null>(null);
const visible = ref(false);

function openPopup() {
  // 使用 ! 操作符确保 ref 已被正确赋值
  popupRef.value!.open();
}
</script>
```

## 📝 注意事项

### 组件开发规范

1. **样式设置**：不要在自定义组件上直接添加 `class` 属性，不同平台存在兼容性问题。推荐使用 `pt` 参数进行样式定制。

2. **标签闭合**：所有组件都必须使用双闭合标签格式，例如：`<cl-button></cl-button>`，禁止使用单闭合标签如 `<cl-button />`。

3. **页面容器**：页面使用 `<cl-page>` 组件包裹，无需手动在最外层包裹 `<scroll-view>`。

4. **底部操作栏**：当页面底部需要展示按钮等操作区域时，统一使用 `cl-footer` 组件。

### 类型安全

- 组件参数值必须为合法、准确且符合预期的类型和取值范围
- 使用 `| null` 或 `?` 定义可空属性
- null 值判断必须使用严格相等 `===` 或 `!==`

### 平台兼容性

- APP 端不支持通过父级样式修改控制子元素样式，需要为子元素单独添加响应式类名
- 为避免鸿蒙平台的渲染异常，建议手动设置过渡属性

## 📚 更多资源

- 📖 [组件文档](https://unix.cool-js.com/src/components/doc.html) - 查看完整的组件 API 文档
- 🛠️ [配置指南](https://unix.cool-js.com/src/guide/config.html) - 了解项目配置
- 🎨 [主题定制](https://unix.cool-js.com/src/introduce/theme.html) - 学习主题定制
- 🔧 [兼容问题](https://unix.cool-js.com/src/introduce/help.html) - 了解兼容性问题

## 💡 示例代码

更多使用示例请参考项目中的 `/pages/demo` 目录，其中包含了所有组件的详细示例代码。

```bash
# 查看组件示例
pages/demo/
├── basic/          # 基础组件示例
├── form/           # 表单组件示例
├── layout/         # 布局组件示例
├── data/           # 数据展示组件示例
├── feedback/       # 反馈组件示例
└── status/         # 状态组件示例
```

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来帮助改进 Cool Unix 组件库！

---

**Cool Unix** - 让跨端开发更简单 🚀

