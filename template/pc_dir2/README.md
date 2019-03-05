# 目录结构说明

```bash
pc_dir2 # 项目名称
├── README.md
├── dist  # 项目发布目录（压缩、合并后的代码）
│   ├── css
│   ├── img
│   ├── index.html
│   └── js
└── src # 项目开发目录（源代码）
    ├── about.html  # 关于页面
    ├── contact.html  # 联系页面
    ├── css
    │   ├── base.css    # 基础样式（包含reset样式、原子性样式），与项目、功能无关的基础样式（所有项目均可使用）
    │   ├── common.css  # 项目公共模块的样式（同一个项目不同页面使用）
    │   ├── page_about.css  # 关于页面样式
    │   ├── page_contact.css  # 联系页面样式
    │   ├── page_details.css  # 详情页面样式
    │   ├── page_index.css  # 首页样式
    │   └── page_promote.css  # 推广页面样式
    ├── details.html  # 详情页面
    ├── img # 图片文件目录（通过目录区分不同页面图片）
    │   ├── about # 关于页面图片
    │   │   ├── about1.png
    │   │   └── about2.ico
    │   ├── common1.png
    │   ├── common2.png
    │   ├── contact # 联系图片
    │   │   ├── contact1.png
    │   │   └── contact2.png
    │   ├── details # 详情页面图片
    │   │   ├── details1.png
    │   │   └── details2.png
    │   ├── index # 首页图片
    │   │   ├── index1.png
    │   │   └── index2.png
    │   └── promote # 推广图片
    │       ├── promote1.png
    │       └── promote2.png
    ├── index.html  # 首页
    ├── js  # js脚本文件目录
    │   ├── jquery-1.12.4.min.js
    │   ├── page_about.js
    │   ├── page_contact.js
    │   ├── page_details.js
    │   ├── page_index.js
    │   └── page_promote.js
    └── promote.html  # 推广页面
```
> base.css: [PC](../../resources/baseforpc.css) [H5](../../resources/baseforh5.css)