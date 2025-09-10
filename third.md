```mermaid
%%{ init: { "flowchart": { "curve": "linear" } } }%%
graph TD
    A[API请求] -->|HTTP Request| B[Express路由层]
    B -->|解析参数| C[控制器层]
    
    C -->|用户操作| D[用户数据处理]
    D -->|INSERT| E[(users表)]
    D -->|UPDATE| F[(users表)]
    D -->|SELECT| G[(users表)]
    
    C -->|内容操作| H[内容数据处理]
    H -->|INSERT| I[(news表)]
    H -->|UPDATE| J[(news表)]  
    H -->|SELECT| K[(news表)]
    H -->|INSERT| L[(products表)]
    H -->|UPDATE| M[(products表)]
    H -->|SELECT| N[(products表)]
    
    C -->|文件处理| O[文件操作模块]
    O -->|上传验证| P[文件格式检查]
    P -->|存储| Q[文件系统]
    P -->|路径记录| R[(files表)]
    
    C -->|权限检查| S[JWT验证模块]
    S -->|解析令牌| T[权限解析]
    T -->|角色验证| U[(roles表)]
    
    E -->|返回ID| V[JSON响应]
    F -->|更新状态| V
    G -->|查询结果| V
    I -->|新闻ID| V
    J -->|更新状态| V
    K -->|新闻列表| V
    L -->|产品ID| V
    M -->|更新状态| V
    N -->|产品列表| V
    Q -->|文件路径| V
    U -->|权限结果| V
    
    V -->|HTTP Response| W[前端页面]
    
    style A fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    style B fill:#fff3e0,stroke:#f57c00,stroke-width:2px
    style C fill:#e8f5e8,stroke:#388e3c,stroke-width:2px
    
    style D fill:#ffebee,stroke:#d32f2f,stroke-width:2px
    style H fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    style O fill:#f1f8e9,stroke:#689f38,stroke-width:2px
    style S fill:#fce4ec,stroke:#c2185b,stroke-width:2px
    
    style E fill:#fff8e1,stroke:#fbc02d,stroke-width:1px
    style F fill:#fff8e1,stroke:#fbc02d,stroke-width:1px
    style G fill:#fff8e1,stroke:#fbc02d,stroke-width:1px
    style I fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style J fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style K fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style L fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style M fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style N fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    style R fill:#f9fbe7,stroke:#827717,stroke-width:1px
    style U fill:#fef7ff,stroke:#6a1b9a,stroke-width:1px
    
    style V fill:#e8f5e8,stroke:#388e3c,stroke-width:3px
    style W fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
