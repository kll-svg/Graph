graph TB
    A[管理员] --> B[新闻管理系统]
    C[普通用户] --> B
    D[游客] --> B
    
    B --> E[(用户数据库)]
    B --> F[(内容数据库)]
    B --> G[(日志数据库)]
    
    E --> H[用户数据反馈]
    F --> I[内容数据反馈] 
    G --> J[日志数据反馈]
    
    H --> A
    H --> C
    H --> D
    I --> A
    I --> C
    I --> D
    J --> A
    
    style A fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    style C fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    style D fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    style B fill:#e8f5e8,stroke:#388e3c,stroke-width:3px
    style E fill:#fff8e1,stroke:#fbc02d,stroke-width:2px
    style F fill:#fce4ec,stroke:#c2185b,stroke-width:2px
    style G fill:#f1f8e9,stroke:#689f38,stroke-width:2px
