# Social Links Hover 动画效果计划

## 目标
为 Social Links 图标添加鼠标悬停时的动画效果，提升交互体验。

## 动画效果选项

### 方案1: 缩放效果 (Scale)
- 鼠标悬停时图标放大 1.1-1.2 倍
- 平滑过渡动画
- 简单优雅，适合大多数场景

### 方案2: 上浮效果 (Lift)
- 鼠标悬停时图标向上移动 2-4px
- 添加轻微阴影
- 营造悬浮感

### 方案3: 颜色变化 (Color Change)
- 鼠标悬停时图标颜色变化
- 可以变为品牌主色或高亮色
- 视觉反馈明显

### 方案4: 旋转效果 (Rotate)
- 鼠标悬停时轻微旋转 5-10 度
- 活泼有趣的效果
- 适合年轻化品牌

### 方案5: 组合效果 (Combined)
- 缩放 + 颜色变化
- 缩放 + 上浮
- 最丰富的视觉反馈

## 推荐方案
**方案5: 缩放 + 颜色变化**
- 悬停时图标放大 1.15 倍
- 颜色变为品牌主色
- 过渡时间 200-300ms
- 使用 ease-out 缓动函数

## 实施步骤

### 1. 修改 header-top.liquid 的 CSS
在 `{% stylesheet %}` 部分添加 hover 动画样式：

```css
.social-icons__icon-wrapper {
  transition: transform 200ms ease-out, opacity 200ms ease-out;
}

.social-icons__icon-wrapper:hover {
  transform: scale(1.15);
}

.social-icons__icon-wrapper a {
  transition: color 200ms ease-out;
}

.social-icons__icon-wrapper:hover a {
  color: var(--color-primary);
}

.social-icons__icon {
  transition: transform 200ms ease-out;
}

.social-icons__icon-wrapper:hover .social-icons__icon {
  transform: scale(1.15);
}
```

### 2. 修改 blocks/social-links.liquid 的 CSS
同样添加 hover 动画样式，保持一致性。

### 3. 可选：添加点击效果
```css
.social-icons__icon-wrapper:active {
  transform: scale(0.95);
}
```

## 文件修改清单
- [ ] `sections/header-top.liquid` - 添加 hover 动画 CSS
- [ ] `blocks/social-links.liquid` - 添加 hover 动画 CSS

## 预期效果
- 鼠标悬停在社交图标上时，图标会平滑放大并改变颜色
- 移开鼠标时，图标平滑恢复原状
- 提升用户交互体验，让界面更生动
