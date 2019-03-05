> **注意：此文档为模板文档，请根据项目实际情况修改并删除此行，【】内容修改后请删除括号。**

# 【项目名称】

【项目简介、描述信息】

## 如何运行

> node 版本 `>=6.xx.xx` <br>
> 【其他】

```bash
# 安装依赖
npm install
# 或使用 yarn
yarn

# 开发
npm run dev

# 预发布（上测试）打包
npm run pre

# 发布（上线）打包
npm run build

# 发布打包分析
npm run builda

```

【其他说明】

## 项目维护

| 角色     | 人员           |
| -------- | -------------- |
| 前端开发 | 【xxx】【yyy】 |
| 后端开发 | 【xxx】        |
| 产品经理 | 【xxx】        |
| 交互设计 | 【xxx】        |

### 需求文档说明

- 【[需求文档](https://xxx)】
- 【[数据接口](https://xxx)】
- 【[设计稿](https://xxx)】

## 业务介绍

【业务描述】

### 页面信息

| 页面目录  | 页面描述     | 页面链接                                 | 参数描述 |
| --------- | ------------ | ---------------------------------------- | -------- |
| 【index】 | 【首页】     | 【[https://xxx.com](https://xxx.com/)】  | 【...】  |
| 【index】 | 【测试地址】 | 【[https://xxx.com/](https://xxx.com/)】 | 【...】  |
| 【index】 | 【线上地址】 | 【[https://xxx.com](https://xxx.com/)】  | 【...】  |

## 项目结构说明

> 以下是举例说明，请根据实际情况修改，请删除此行。

- `/src`：源代码目录
- `/dist`：线上打包代码目录
- 【其他】

```bash
.
├── .eslintrc.js  # eslint配置文件
├── .prettierrc.js  # prettier配置文件
├── build # webpack配置文件目录
├── dist # 上线打包目录
├── pre # 预发布打包目录
└── src # 源码目录
    ├── api # 公共接口、日志处理目录（代码组织方式供参考）
    ├── common  # 公共资源目录
    │   ├── css # 公共样式资源
    │   └── js  # 公共js资源
    ├── css # 页面css
    ├── img # 图片
    ├── index.html  # 入口模板
    └── js  # 业务js目录
        ├── index.js  # 入口js
```

## 其他事项

补充说明

> 【项目备注】
