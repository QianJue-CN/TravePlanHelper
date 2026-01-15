# 智能旅游规划助手 (TravelPlanHelper)

## 📖 项目简介
**TravelPlanHelper** 是一个基于 **MCP (Model Context Protocol)** 架构构建的专业智能旅游规划系统。它不仅仅是一个简单的问答机器人，而是一个集成了实时交通、地图导航、天气查询、社区攻略（小红书）、搜索引擎以及数据可视化等多种强大工具的智能体。

本项目的核心目标是为用户提供 **真实、可行、个性化且深度** 的旅游解决方案，从灵感启发到最终的落地执行，提供全流程支持。

## ✨ 核心能力 (Core Capabilities)

基于 `skills/travel-planner` 中定义的专业技能，本助手具备以下核心能力：

| 能力 | 图标 | 说明 |
| :--- | :--- | :--- |
| **旅游线路规划** | 🗺️ | 基于地理位置 (AMap) 和时间维度的最优路线规划 |
| **交通方案优化** | 🚗 | 整合火车 (12306)、航班 (VariFlight) 及本地交通的多模式出行建议 |
| **住宿与美食推荐** | 🏨/🍜 | 结合位置便利性与真实用户评价 (小红书/搜索) 的精选推荐 |
| **深度景点解析** | 🎯 | 提供景点的文化背景、游玩攻略及实时状态信息 |
| **预算控制与可视化** | 💰 | 精确到项目的成本管控，并生成直观的饼图、甘特图等统计图表 |
| **全方位避雷指南** | ⚠️ | 基于海量真实用户反馈，提供住宿、餐饮、交通等方面的风险预警 |

## 🛠️ 集成 MCP 工具 (Integrated Tools)

本项目通过 MCP 协议集成了丰富的外部工具，赋予了 AI 强大的“手脚”：

*   **核心思维与搜索**
    *   `sequential-thinking`: 赋予 AI 深度思考、逻辑分析和多步规划的能力。
    *   `tavily-mcp` / `searxng`: 强大的网络搜索能力，用于获取官方资讯和广域信息。
    *   `fetch`: 用于抓取特定网页内容进行深度阅读。

*   **垂直领域数据**
    *   `xiaohongshu-mcp`: 搜索小红书笔记，获取最真实的游客体验、网红打卡点及避雷信息。
    *   `12306-mcp`: 中国铁路列车时刻与票务查询。
    *   `variflight-mcp`: 全球航班动态与票务信息查询。
    *   `amap` (高德地图): 地点搜索、路径规划与交通耗时估算。
    *   `OpenWeatherMCP`: 目的地实时天气与未来预报，辅助穿衣与行程安排。

*   **实用工具**
    *   `time`: 获取精确的当前时间，确保行程规划的时效性。
    *   `mcp-server-chart`: 生成各类统计图表（饼图、雷达图、甘特图等），实现攻略的可视化。
    *   `mcp-file-downloader`: 将生成的图表等资源保存到本地，丰富攻略文档。

## 🚀 使用流程 (Workflow)

Travel Planner 遵循严谨的 `skills/travel-planner/SKILL.md` 工作流：

1.  **Phase 0: 智能工具自检**
    *   系统自动检测可用 MCP 工具状态，确定当前服务能力范围。
    *   校准时间服务，确保票务查询准确性。

2.  **Phase 1: 智能信息收集**
    *   通过对话引导用户明确 **出发地、目的地、时间、预算、人数** 等关键要素。
    *   挖掘用户的饮食偏好、住宿要求等个性化需求。

3.  **Phase 2: 深度规划与生成**
    *   **多源搜集**: 结合官方信息与社区攻略（小红书）。
    *   **交叉验证**: 验证景点开放时间、票价及交通可行性。
    *   **图表生成**: 自动绘制行程甘特图、预算占比图、景点雷达图。
    *   **攻略输出**: 生成包含 11 个标准板块的完整 Markdown 格式旅游攻略。

## 📂 目录结构说明

*   `skills/`: 存放 AI 智能体的技能定义文件。
    *   `travel-planner/`: 核心旅游规划师技能包。
        *   `SKILL.md`: 技能定义、角色设定及工作流规范。
        *   `assets/`: 包含图表定义 (Mermaid)、输出模板等资源。
        *   `references/`: 详细的参考文档。
*   `images/`: 存放规划过程中生成的图表和下载的资源文件。

## 🔗 参考链接 (References)

以下是本项目集成的 MCP Server 源码仓库：

*   sequential-thinking: [https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking)
*   OpenWeatherMCP: [https://github.com/QianJue-CN/OpenWeatherMCP](https://github.com/QianJue-CN/OpenWeatherMCP)
*   time: [https://github.com/Taki-Ta/mcp-server-time](https://github.com/Taki-Ta/mcp-server-time)
*   variflight-mcp: [https://github.com/variflight/variflight-mcp](https://github.com/variflight/variflight-mcp)
*   12306-mcp: [https://github.com/Joooook/12306-mcp](https://github.com/Joooook/12306-mcp)
*   amap: [https://github.com/zxypro1/amap-maps-mcp-server](https://github.com/zxypro1/amap-maps-mcp-server)
*   fetch: [https://github.com/modelcontextprotocol/servers/tree/main/src/fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch)
*   tavily-mcp: [https://github.com/tavily-ai/tavily-mcp](https://github.com/tavily-ai/tavily-mcp)
*   searxng: [https://github.com/jae-jae/searxng-mul-mcp](https://github.com/jae-jae/searxng-mul-mcp)
*   mcp-server-chart: [https://github.com/antvis/mcp-server-chart](https://github.com/antvis/mcp-server-chart)
*   xiaohongshu-mcp: [https://github.com/xpzouying/xiaohongshu-mcp](https://github.com/xpzouying/xiaohongshu-mcp)
*   mcp-file-downloader: [https://github.com/QianJue-CN/DownLoadMCP](https://github.com/QianJue-CN/DownLoadMCP)
