# 九人宜兴-湖州自驾游记

> 一家九口（6老+2大+1小）春节六日五晚自驾之旅的图文记录

## 📂 项目结构

```
travel-blog/
├── index.html           # 主网页（部署到 GitHub Pages）
├── 公众号文章-第一天.md  # 公众号文章（第一天）
├── images/              # 图片目录（需创建）
└── README.md           # 本文件
```

## 🚀 部署到 GitHub Pages

### 方法一：使用 GitHub 网页操作

1. **创建 GitHub 仓库**
   - 访问 https://github.com/new
   - 仓库名建议：`travel-blog-yixing-huzhou` 或 `family-trip-2026`
   - 选择 Public（公开）
   - 勾选 "Add a README file"

2. **上传文件**
   - 点击仓库中的 "uploading an existing file"
   - 将 `index.html` 拖拽上传
   - 在页面底部填写提交信息，点击 "Commit changes"

3. **启用 GitHub Pages**
   - 进入仓库的 **Settings**（设置）
   - 左侧菜单找到 **Pages**
   - 在 "Build and deployment" 下：
     - Source 选择：**Deploy from a branch**
     - Branch 选择：**main** (或 master) 和 **/ (root)**
   - 点击 **Save**

4. **访问网站**
   - 等待 1-2 分钟
   - 访问 `https://你的用户名.github.io/仓库名/`
   - 例如：`https://username.github.io/travel-blog-yixing-huzhou/`

### 方法二：使用 Git 命令行

```bash
# 1. 创建本地 Git 仓库
cd "C:\claude\travel-blog"
git init

# 2. 添加所有文件
git add .

# 3. 提交
git commit -m "第一天：宜兴窑湖小镇小火车与烟花秀"

# 4. 在 GitHub 上创建仓库后，关联远程仓库
git remote add origin https://github.com/你的用户名/travel-blog-yixing-huzhou.git

# 5. 推送到 GitHub
git branch -M main
git push -u origin main

# 6. 在 GitHub 仓库设置中启用 Pages（同方法一第3步）
```

## 📷 关于图片

### 当前状态
网页中使用的是本地绝对路径（`C:\迅雷下载\图片临时保存\...`），仅在本地可查看。

### 部署后显示图片的三种方法

#### 方法一：使用图床服务（推荐）

1. **上传图片到图床**
   - 推荐：[ImgGo](https://imgse.com)、[图壳](https://imgkr.com)、[Cloudinary](https://cloudinary.com)
   - 将 `C:\迅雷下载\图片临时保存` 目录下的图片上传

2. **替换网页中的图片路径**
   - 将图床返回的 URL 替换 `index.html` 中的本地路径
   - 例如将：
     ```html
     <img src="C:\迅雷下载\图片临时保存\微信图片_20260214163744_103_654.jpg" alt="出发前">
     ```
     替换为：
     ```html
     <img src="https://your-image-url.com/微信图片_20260214163744_103_654.jpg" alt="出发前">
     ```

#### 方法二：使用 GitHub 仓库存储图片

1. **创建 images 目录**
   ```bash
   mkdir images
   ```

2. **将图片复制到 images 目录**
   - 手动复制或使用命令：
     ```bash
     xcopy "C:\迅雷下载\图片临时保存\*.jpg" "images\"
     ```

3. **修改 index.html 中的图片路径**
   - 将 `C:\迅雷下载\图片临时保存\` 替换为 `images/`
   - 批量替换（使用编辑器查找替换）：
     - 查找：`C:\迅雷下载\图片临时保存\`
     - 替换为：`images/`

4. **一起上传到 GitHub**

#### 方法三：使用 GitHub Releases + jsDelivr CDN

1. **在 GitHub 仓库创建 Release**
   - 进入仓库 → Releases → "Create a new release"
   - 上传包含图片的 zip 文件

2. **使用 jsDelivr CDN 链接**
   - 格式：`https://cdn.jsdelivr.net/gh/用户名/仓库名@版本号/images/图片名.jpg`
   - 示例：`https://cdn.jsdelivr.net/gh/username/travel-blog@v1/images/photo.jpg`

## 📹 关于视频

由于视频文件较大（超过 8MB），需要手动处理截图。您有以下选择：

### 选项一：手动截图（简单）
1. 用视频播放器打开视频
2. 暂停在精彩瞬间
3. 使用截图工具（Windows: Win+Shift+S）截图
4. 将截图保存到图片目录，并在网页/公众号中使用

### 选项二：使用命令行工具
需要先安装 [ffmpeg](https://ffmpeg.org/)：
```bash
# 安装后使用以下命令从视频中截取帧
ffmpeg -i "视频文件路径.mp4" -ss 00:00:05 -vframes 1 "输出图片.jpg"
```

### 选项三：上传到视频平台
- 上传到微信视频号、腾讯视频等平台
- 在公众号文章中嵌入视频链接

## 📝 公众号文章使用指南

1. **复制内容**
   - 打开 `公众号文章-第一天.md`
   - 复制全部内容

2. **粘贴到公众号编辑器**
   - 登录 [微信公众平台](https://mp.weixin.qq.com)
   - 新建图文
   - 粘贴内容（格式会自动保留）

3. **上传图片**
   - 选择文中所有的本地图片路径引用
   - 使用公众号编辑器的"插入图片"功能上传对应图片

4. **调整格式**
   - 根据公众号编辑器的样式微调
   - 建议使用微信官方的排版样式

## 🎨 自定义修改

### 更改颜色主题
编辑 `index.html` 中的 CSS 变量：
```css
:root {
    --primary-color: #e07a5f;    /* 主色调 */
    --secondary-color: #3d405b;  /* 次要色 */
    --accent-color: #81b29a;     /* 强调色 */
    --bg-color: #f4f1de;         /* 背景色 */
}
```

### 添加新的一天
1. 复制 `<div class="section">...</div>` 区块
2. 修改标题和内容
3. 添加对应照片

## 📞 联系方式

如有问题，欢迎反馈！

---

**祝您旅途愉快，记录美好回忆！** 🌟
