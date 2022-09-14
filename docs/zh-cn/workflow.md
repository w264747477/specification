# 工作流规范

## 版本控制

- 采用三位版本后控制，初始版本号 <font color="#e96900">1.0.0</font>
- 主版本号：当你做了不兼容的<font color="#e96900">API</font> 修改
- 次版本号：当你做了向下兼容的功能性新增
- 修订号：当你做了向下兼容的问题修正

## git 控制

### 团队约定

- <font color="#e96900">develop </font> 开发分支-主分支，用于开发阶段
- <font color="#e96900">develop-os1.9 </font> 开发分支-特定功能分支，用于不同业务需求同时开发（上线完成后，需要将此分支合并到 develop）
- <font color="#e96900">feature </font> 分支，用于测试阶段（develop 分支推送到 feature 分支，根据不同业务上线时间，先上线的先推送测试）
- <font color="#e96900">master</font> 分支，主分支，<font color="#e96900">feature </font> 测试完成推送到 <font color="#e96900">master </font> 分支
- <font color="#e96900">release</font> 分支，从 <font color="#e96900">master</font> 分支创建用于产品发布的分支，格式为 <font color="#e96900">v1.0.0</font>
- <font color="#e96900">release-fix2022.10.20</font> 分支，从 <font color="#e96900">release</font> 分支创建用于已上线分支 bug 修复或优化(修复完成后，需要将代码合并到 develop 分支)

## 提交规范

| 命令     | 功能                                              |
| -------- | ------------------------------------------------- |
| feat     | 新功能（feature）                                 |
| fix      | 修补 bug                                          |
| docs     | 文档（documentation）                             |
| style    | 格式（不影响代码运行的变动）                      |
| refactor | 重构（即不是新增功能，也不是修改 bug 的代码变动） |
| test     | 增加测试                                          |
| chore    | 构建过程或辅助工具的变动                          |

## 构建规范

使用 <font color="#e96900">vue-cli</font> 进行构建

## 发布规范

- 正式环境
  - 通过效能平台搭建正式环境构建，通过正式环境构建生成上线镜像
- 测试环境
  - 通过效能平台搭建测试环境构建、流水线、应用，每次更新代码通过流水线进行测试环境的更新
