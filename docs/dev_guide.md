 
┌─────────────────┐     ┌─────────────────┐
│   Web Client    │◄───►│  API Service    │
│ (Streamlit/Web) │     │ (FastAPI/REST)  │
└─────────────────┘     └───────┬─────────┘
                                │
                                ▼
┌───────────────────────────────────────────┐
│              AI Core Service              │
│  ┌─────────────┐    ┌─────────────┐       │
│  │ Code Analyzer│◄──►│ LLM Gateway │       │
│  └─────────────┘    └─────────────┘       │
└───────────────────────────────────────────┘
                                ▲
                                │
┌─────────────────┐     ┌───────┴─────────┐
│  Data Storage   │◄────┤  Knowledge Base │
│ (SQLAlchemy)    │     │  (RAG/Graph)    │
└─────────────────┘     └─────────────────┘
EduX/
├── .github/                  # CI/CD配置
│   └── workflows/
├── config/                   # 配置隔离
│   ├── __init__.py
│   ├── settings.py          # 配置类（OOP）
│   └── prompts/             # 多语言提示词模板
├── docs/
│   ├── i18n/                # 多语言文档
│   │   ├── README.zh-CN.md
│   │   └── README.ja.md
│   └── dev_guide.md         # 开发指南
├── src/
│   ├── api/                 # API层
│   │   ├── routers/         # 路由模块
│   │   └── schemas.py       # Pydantic模型
│   ├── ai_core/             # AI核心（OOP设计）
│   │   ├── analyzers/       # 代码分析器
│   │   │   └── python_analyzer.py # 类继承体系
│   │   └── llm/
│   │       ├── base_llm.py  # 抽象类
│   │       └── openai_adapter.py # 具体实现
│   ├── data_models/         # 数据库模型
│   │   └── user_model.py    # SQLAlchemy类
│   ├── services/            # 业务逻辑层
│   │   ├── learning_service.py # 类方法
│   │   └── assessment_service.py
│   └── utils/               # 工具类
│       └── logger.py        # 日志工具类
├── tests/                   # 分层测试
│   ├── unit/                # 单元测试
│   └── integration/         # 集成测试
├── requirements.txt         # PIP依赖
├── Dockerfile               # 容器化
├── README.md                # 英文主文档
└── README.zh-CN.md          # 中文文档
