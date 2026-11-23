# 徐天浩 · 个人主页

这个仓库只有一个目的：放一个别人能直接打开看的网页。

上线地址：**https://xthyi.github.io**

## 这个页面是什么

一个单文件网页（`index.html`），里面有：

- 一句自我介绍
- 一列「链接」卡片，点一下就跳走
- 一列「项目」卡片，说明我在做什么
- 右上角能在浅色和深色之间切换，选过会记住

整页不依赖任何外部资源，没有 CDN、没有字体下载，断网打开也一样。

## 怎么改

### 加一个链接

用任何文本编辑器打开 `index.html`，翻到最下面的 `<script>`，找到 `LINKS`：

```js
const LINKS = [
  { name: "GitHub 主页", desc: "代码都在这里", url: "https://github.com/Xthyi" },
];
```

照着加一行就行：

```js
  { name: "我的B站", desc: "偶尔发视频", url: "https://space.bilibili.com/xxx" },
```

注意逗号别漏，加完保存、刷新页面就能看到。

### 改项目和自我介绍

`<section>` 里的 `.card` 就是项目卡片，`.intro` 就是那段自我介绍，直接改文字即可。

### 改配色

文件开头的 `:root` 和 `html[data-theme="dark"]` 是两套颜色，`--accent` 是主色（现在是灰绿色）。

## 怎么更新到线上

改完文件后，在终端里：

```bash
cd ~/Documents/my-site
git add -A
git commit -m "更新内容"
git push
```

推上去大约半分钟到一分钟，https://xthyi.github.io 就会更新。

## 说明

- `index.html`：页面本体
- `.nojekyll`：告诉 GitHub 不要用 Jekyll 处理，原样发布，删掉可能出问题
