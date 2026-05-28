---
name: resume-generator
description: 将 JSON 数据渲染为左栏个人信息 + 右栏经历的 A4 单页简历 HTML，用户 Ctrl+P 打印为 PDF。使用此技能当：生成简历网页、做个简历、左栏右栏简历。"Use this" skill to generate a resume webpage in A4 layout.
---

# resume-generator

将一份结构化 JSON 数据渲染为"左栏个人信息 + 右栏经历结构"的单页 A4 简历 HTML，用户通过浏览器打印为 PDF。

## 触发词

简历网页、生成简历网页、做个简历、resume webpage、generate resume、简历 skill、"左栏右栏"简历

## 输入

用户提供一份 JSON 对象，字段定义见 `references/data-schema.md`。

## 布局规格

```
A4 尺寸：210mm × 297mm
侧边栏：255px（约30%）
主内容栏：flex: 1（自适应）
总宽度：≈ 718px（不含浏览器默认左右margin）
总高度：1045px（固定，overflow: hidden）
```

## 步骤

1. 读取 `templates/template.html` 骨架
2. 读取 `assets/resume.css` 样式
3. 按 `references/data-schema.md` 将 JSON 字段映射填入 HTML 占位符
4. 输出完整 HTML 到用户指定路径或临时目录
5. 告知用户 `Ctrl+P → 另存为 PDF`

## 输出合约

- 输出一个 `.html` 文件
- 浏览器打印预览正好一张 A4，不溢出、不分页
- 左侧栏：证件照占位 + 姓名 + 联系方式 + 爱好 + 兴趣圆形标签
- 右侧栏：教育经历 → 工作经历 → 项目经历 → 荣誉证书 → 个人技能
- 颜色主题：深蓝 `#1a3a5c` 主色 + 白底黑字

## 失败处理

- 缺少必填字段：提示用户补充，不生成残缺页面
- 内容过多导致溢出：自动压缩行高和间距（CSS flex-shrink），但字体不小于 11px
- 无 JSON 时：询问用户提供数据，可接受直接粘贴文字描述由模型结构化