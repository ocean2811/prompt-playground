# 🤖 AI提示词调试

一个简洁而强大的AI提示词调试工具，支持实时测试和优化AI提示词，帮助开发者快速验证提示词效果。

![GitHub](https://img.shields.io/github/license/ocean2811/prompt-playground)
![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## ✨ 特性

### 🚀 核心功能
- **实时流式回答** - 支持SSE流式传输，实时显示AI回答过程
- **多模型支持** - 兼容OpenAI API格式的各种AI模型（OpenAI、Qwen、Ollama、Claude(通过oaipro等工具转换为openai兼容格式后)等）
- **双提示词模式** - 分别配置系统提示词和用户提示词
- **参数精细调控** - 支持温度、最大Token数、回答格式等参数调节

### 💾 智能配置
- **自动保存配置** - 所有配置项自动保存到本地存储，无需重复输入
- **配置持久化** - API密钥、模型参数、提示词内容自动恢复
- **一键清空** - 快速清空所有输入内容重新开始

### 📊 详细统计
- **实时字符计数** - 显示提示词和回答的字符数量
- **请求耗时统计** - 精确计算请求响应时间
- **Token使用量** - 显示输入和输出Token消耗
- **费用计算** - 根据模型定价自动计算请求费用

### 🎨 用户体验
- **响应式设计** - 完美适配桌面和移动设备
- **可收缩侧边栏** - 节省屏幕空间，专注内容创作
- **一键复制** - 快速复制AI回答内容
- **快捷键支持** - Ctrl+Enter快速发送请求
- **实时状态显示** - 清晰的请求状态和错误提示

### 🔒 安全可靠
- **纯前端实现** - 无需服务器，本地运行更安全
- **API密钥本地存储** - 敏感信息仅保存在本地浏览器
- **请求控制** - 支持随时停止正在进行的请求

## 🛠️ 安装使用

### 方式一：直接使用
1. 下载 `prompt-playground.html` 文件
2. 用浏览器打开文件即可使用
3. 无需安装任何依赖或服务器

### 方式二：本地服务器
```bash
# 克隆项目
git clone https://github.com/ocean2811/prompt-playground.git
cd prompt-playground

# 启动本地服务器（可选）
python -m http.server 8000
# 或使用Node.js
npx serve .

# 访问 http://localhost:8000
```

## 📖 使用指南

### 1. 配置API信息
在左侧配置面板中填入：
- **Base URL**: API服务地址（如：`https://dashscope.aliyuncs.com/compatible-mode/v1`）
- **API Key**: 你的API密钥
- **模型**: 要使用的AI模型名称（如：`qwen-max`）

### 2. 设置模型参数
- **温度 (0-2)**: 控制回答的随机性，越高越有创意
- **最大Token数**: 限制回答的最大长度
- **回答格式**: 选择Text、JSON Object或JSON Schema(暂未支持)

### 3. 编写提示词
- **系统提示词**: 设定AI的角色和行为规则
- **用户提示词**: 具体的问题或任务描述

### 4. 发送请求
- 点击 "🚀 发送请求" 按钮
- 或使用快捷键 `Ctrl + Enter`
- 实时查看AI回答和统计信息

### 5. 管理结果
- 使用 "📋 复制" 按钮复制回答内容
- 查看详细的使用统计和费用信息
- 使用 "🗑️ 清空" 重新开始

## 🔧 配置说明

### 支持的AI服务
| 服务商 | Base URL | 支持模型 |
|--------|----------|----------|
| 阿里云通义千问 | `https://dashscope.aliyuncs.com/compatible-mode/v1` | qwen-max, qwen-plus |
| OpenAI | `https://api.openai.com/v1` | gpt-4, gpt-3.5-turbo |
| 本地部署（ollama等） | `http://localhost:11434/v1` | 自定义模型 |
| 其他兼容OpenAI格式 | `https://xxx.com/v1` | xxx |

### 费用计算
工具内置了主流模型的定价信息，自动计算：
- 输入Token费用
- 输出Token费用
- 总计费用（人民币）

支持的计费模型包括：
- Qwen系列模型
- Claude系列模型
- 可自定义添加其他模型定价(详见源码的`pricingMap`)

## 🎯 使用场景

### 提示词工程师
- 快速测试不同的提示词策略
- 对比系统提示词和用户提示词的效果
- 优化提示词以获得更好的AI回答

### AI应用开发者
- 验证API集成的正确性
- 测试不同模型的表现差异
- 调试AI应用中的提示词问题

### 内容创作者
- 使用AI辅助创作内容
- 尝试不同的创作角度和风格
- 快速生成创意素材

### 研究人员
- 对比不同AI模型的能力
- 研究提示词对输出质量的影响
- 收集AI回答数据进行分析

## 🔧 技术实现

### 技术栈
- **前端**: 纯HTML5 + CSS3 + Vanilla JavaScript
- **存储**: localStorage (本地存储)
- **通信**: Fetch API + Server-Sent Events
- **样式**: 原生CSS + Flexbox + Grid

### 核心特性实现
- **流式传输**: 使用ReadableStream处理SSE响应
- **配置持久化**: localStorage自动保存用户配置
- **响应式布局**: CSS Grid + Flexbox实现自适应
- **实时统计**: JavaScript计算Token和费用信息

## 🤝 贡献指南

欢迎贡献代码、报告问题或提出改进建议！

### 开发环境
1. Fork 项目到你的GitHub账户
2. 克隆fork的项目到本地
3. 创建新的功能分支
4. 提交你的更改
5. 推送到GitHub并创建Pull Request

### 提交规范
- feat: 新功能
- fix: 修复问题
- docs: 文档更新
- style: 代码格式调整
- refactor: 代码重构
- test: 测试相关
- chore: 构建或工具相关

## 📄 许可证

本项目采用 [MIT License](LICENSE) 开源协议。

## 📞 联系方式

如果你有任何问题或建议，欢迎通过以下方式联系：

- GitHub Issues: [提交问题](https://github.com/ocean2811/prompt-playground/issues)
- Email: ocean2811@outlook.com

---

⭐ 如果这个项目对你有帮助，请给个星标支持一下！
