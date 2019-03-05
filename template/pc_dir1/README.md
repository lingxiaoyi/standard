# 目录结构说明

```bash
pc_dir1 # 项目名称
├── dist  # 项目发布目录（压缩、合并后的代码）
│   ├── css
│   ├── img
│   ├── index.html
│   └── js
└── src # 项目开发目录（源代码）
    ├── about.html  # 关于页面
    ├── contact.html
    ├── css # css样式文件目录
    │   ├── base.css  # 基础样式（包含reset样式、原子性样式），与项目、功能无关的基础样式（所有项目均可使用）
    │   ├── common.css  # 项目公共模块的样式（同一个项目不同页面使用）
    │   └── page.css  # 具体业务样式（内含该项目所有页面的样式，通过css注释区分不同页面样式）
    ├── img # 图片文件目录（用于存放项目用到的所有图片）
    │   ├── img1.png
    │   └── img2.png
    ├── index.html  # 首页
    └── js  # js脚本文件目录
        ├── jquery-1.12.4.min.js  # js库文件（针对我们目前的项目、业务，考虑到兼容性更强建议采用jquery 1.x版本进行开发，移动端建议使用ZeptoJS。）
        ├── page_about.js # 关于页面js
        ├── page_contact.js
        └── page_index.js # 首页js
```
> base.css: [PC](../../resources/baseforpc.css) [H5](../../resources/baseforh5.css)