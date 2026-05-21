# ZMQ_Q 个人网站 — 使用说明

## 目录结构
```
zmq_site/
├── index.html              主页面
├── assets/
│   ├── images/             CG作品图 + 视频缩略图（SVG格式，可替换）
│   │   ├── cg_work_1.svg   赛博武者
│   │   ├── cg_work_2.svg   幽冥法师
│   │   ├── cg_work_3.svg   钢铁龙骑
│   │   ├── video_thumb_1~5.svg  视频封面图
│   └── videos/             ← 放你自己的视频文件到这里
└── generate_assets.py      素材重新生成脚本
```

## 替换视频

### 首屏视频（打斗CG）
在 `index.html` 第 ~200 行找到：
```html
<video id="heroVideo" autoplay muted loop playsinline src="" poster="">
```
将 `src=""` 改为你的视频路径，例如：
```html
src="assets/videos/hero_fight.mp4"
```

### 作品视频（点击弹窗播放）
在 `index.html` 底部 JS 的 `videoData` 对象里，填入各视频的 src：
```js
const videoData = {
  1: { title: '暗影裂缝', desc: '...', src: 'assets/videos/shadow_rift.mp4' },
  2: { title: '烈焰协议', desc: '...', src: 'assets/videos/flame_protocol.mp4' },
  ...
};
```

## 替换CG作品图
直接替换 `assets/images/` 下的 svg 文件，或改 `<object data="...">` 的路径指向你的 PNG/JPG/WebP。

## 支持的图片格式
SVG、PNG、JPG、WebP 均支持，修改 HTML 中 object/img 标签的 src 即可。
