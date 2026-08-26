# 拼图，游戏配件，运动户外 · 标题与图片优化中心

## 📁 项目结构

```
mens-optimization-site/
├── index.html              # 主页（6大模块导航入口）
├── image-optimization.html # 图片优化提示词中心
├── title-optimization.html # 标题优化工具
├── market-demand.html      # 市场需求图片区
├── plan-demand.html        # 企划需求PDF展示
├── assets/
│   ├── css/style.css       # 全局样式
│   ├── js/app.js           # 主页交互逻辑
│   └── pdf/                # PDF文件目录
│       ├── 夹克外套企划款式参考-都市基础风.pdf
│       ├── 夹克外套企划款式参考-工装.pdf
│       ├── 夹克外套企划款式参考-皮衣夹克.pdf
│       ├── 夹克外套企划款式参考-户外机能风.pdf
│       ├── 衬衫企划款式参考-工装衬衫.pdf
│       ├── 衬衫企划款式参考-休闲衬衫.pdf
│       └── 衬衫企划款式参考-商务衬衫.pdf
└── data/                   # 数据文件目录
    ├── category_guide.json      # 类目指引数据（由Excel生成）
    ├── market_demand.json       # 市场需求数据（由Excel生成）
    ├── title_keywords.json      # 标题优化词库
    ├── keyword_library.json     # 分维度枚举词库
    ├── 国 家站点热搜词.txt       # 近期资讯-热搜词
    └── 近期通知.txt              # 近期资讯-通知
```

## 🔄 如何更新内容

### 1. 类目指引
- 更新【类目指引.xlsx】
- 运行数据转换脚本生成 `data/category_guide.json`
- 网页自动加载新数据

### 2. 市场需求图片
- 更新【招品.xlsx】
- 运行数据转换脚本生成 `data/market_demand.json`
- 网页自动加载新数据，按更新时间排序

### 3. 企划需求PDF
- 直接替换 `assets/pdf/` 目录下的PDF文件
- 保持文件名不变即可自动展示
- 如需新增分类，在 plan-demand.html 中添加对应section

### 4. 近期资讯
- 直接修改 `data/国家站点热搜词.txt`
- 直接修改 `data/近期通知.txt`
- 网页自动加载最新内容

### 5. 视觉优化-市场视觉需求PDF
- 将PDF放置于 `assets/pdf/market-visual-demand.pdf`

## 🚀 部署方式（GitHub Pages）

### 方法一：全新仓库（推荐小白）
1. 登录 GitHub，点击 New Repository
2. 仓库名填 `mens-optimization`，选择 Public
3. 不要勾选任何初始化选项
4. 创建后点击 uploading an existing file
5. 将本项目所有文件拖入上传
6. 进入仓库 Settings → Pages
7. Source 选 main 分支，目录选 /root
8. 点击 Save，等待几分钟即可访问

### 方法二：清理旧仓库重新上传
1. 进入旧仓库，删除所有文件
2. 上传本项目所有文件
3. Settings → Pages 确认配置

## 📝 数据转换说明

如需从Excel重新生成JSON数据，需安装Python环境：

```bash
pip install openpyxl
python3 convert_data.py
```

（convert_data.py 为数据转换脚本，可按需创建）

## ⚠️ 注意事项

- 所有图片为外链引用，需确保网络可访问
- PDF文件使用 iframe 内嵌展示，需浏览器支持PDF预览
- 标题优化生成的标题仅供参考，不可直接使用
- 市场需求图片仅供款式参考，不可侵权使用
