# TravelPlanHelper

[中文文档](README_ZH.md)

## 📖 Introduction
**TravelPlanHelper** is a professional intelligent travel planning system built on the **MCP (Model Context Protocol)** architecture. It is more than just a simple chatbot; it is an intelligent agent integrating powerful tools such as real-time traffic, map navigation, weather forecasting, community guides (Xiaohongshu/RED), search engines, and data visualization.

The core objective of this project is to provide users with **authentic, feasible, personalized, and in-depth** travel solutions, supporting the entire process from inspiration to execution.

## ✨ Core Capabilities

Based on the professional skills defined in `skills/travel-planner`, this assistant possesses the following core capabilities:

| Capability | Icon | Description |
| :--- | :--- | :--- |
| **Route Planning** | 🗺️ | Optimal route planning based on geolocation (AMap) and time dimensions |
| **Transport Optimization** | 🚗 | Multi-modal travel suggestions integrating trains (12306), flights (VariFlight), and local transport |
| **Accommodation & Dining** | 🏨/🍜 | Curated recommendations combining location convenience with real user reviews (Xiaohongshu/Search) |
| **Deep Attraction Analysis** | 🎯 | Cultural background, touring guides, and real-time status information for attractions |
| **Budget Control & Viz** | 💰 | Itemized cost control with visual charts like pie charts and Gantt charts |
| **Risk Avoidance** | ⚠️ | Risk warnings for accommodation, dining, and transport based on real user feedback |

## 🛠️ Integrated MCP Tools

This project integrates a rich set of external tools via the MCP protocol, empowering the AI with "hands and feet":

*   **Core Thinking & Search**
    *   `sequential-thinking`: Empowers AI with deep thinking, logical analysis, and multi-step planning capabilities.
    *   `tavily-mcp` / `searxng`: Powerful web search capabilities for official news and broad information.
    *   `fetch`: Used for scraping specific web page content for deep reading.

*   **Vertical Domain Data**
    *   `xiaohongshu-mcp`: Searches Xiaohongshu (RED) notes for authentic tourist experiences, popular spots, and "avoid-pitfall" guides.
    *   `12306-mcp`: China Railway train schedule and ticket inquiries.
    *   `variflight-mcp`: Global flight status and ticket information.
    *   `amap` (AMap/Gaode): Location search, path planning, and travel time estimation.
    *   `OpenWeatherMCP`: Real-time weather and forecasts for destinations to assist with clothing and scheduling.

*   **Utility Tools**
    *   `time`: Gets precise current time to ensure the timeliness of itinerary planning.
    *   `mcp-server-chart`: Generates various statistical charts (Pie, Radar, Gantt, etc.) for itinerary visualization.
    *   `mcp-file-downloader`: Saves generated charts and resources locally to enrich the guide document.

## 🚀 Workflow

The Travel Planner follows the rigorous workflow defined in `skills/travel-planner/SKILL.md`:

1.  **Phase 0: Tool Self-Check**
    *   Automatically detects available MCP tool status to determine current service scope.
    *   Calibrates time services to ensure accuracy in ticket queries.

2.  **Phase 1: Intelligent Information Collection**
    *   Guides users through conversation to clarify key elements: **Origin, Destination, Dates, Budget, People**.
    *   Uncovers personalized needs such as dietary preferences and accommodation requirements.

3.  **Phase 2: Deep Planning & Generation**
    *   **Multi-source Collection**: Combines official information with community guides (Xiaohongshu).
    *   **Cross-Validation**: Verifies opening hours, ticket prices, and transport feasibility.
    *   **Chart Generation**: Automatically draws itinerary Gantt charts, budget pie charts, and attraction radar charts.
    *   **Guide Output**: Generates a complete Markdown travel guide containing 11 standard sections.

## 📂 Directory Structure

*   `skills/`: Contains skill definition files for the AI agent.
    *   `travel-planner/`: Core travel planner skill package.
        *   `SKILL.md`: Skill definition, role settings, and workflow specifications.
        *   `assets/`: Contains chart definitions (Mermaid), output templates, etc.
        *   `references/`: Detailed reference documentation.
*   `images/`: Stores charts generated and resources downloaded during the planning process.

## 🔗 References

Below are the source repositories for the MCP Servers integrated into this project:

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
