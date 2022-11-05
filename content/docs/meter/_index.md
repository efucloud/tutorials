---
bookCollapseSection: true
weight: 20
---

# Meter设计
Meter作为Efu Cloud的测试品牌，集成多种自动化测试工具的产品，包括Mock服务，API自动化测试, BDD自动化测试, Web自动化测试, Jmeter性能测试，K6性能测试，通过Adapter能够跟第三方系统进行对接，能够全方位满足客户需求。
{{< mermaid >}}
flowchart TD
    subgraph "Efu Cloud"
    客户License管理
    产品管理
    end
    subgraph "Meter Adapter"
    消息接收
    Jira对接
    飞书对接
    ....
    end
    subgraph "Meter Center"
    接口文档管理
    消息推送
    测试结果管理
    end
    subgraph "Create Cloud"
    License管理
    用户管理
    end
    subgraph "Mock Runner"
    m启动检查
    Mock服务
    end
    subgraph "Http Runner"
    h启动检查
    Http测试服务
    end
    subgraph "BDD Runner"
    b启动检查
    BDD测试服务
    end
    License管理--1.申请License-->客户License管理
    License管理--3.License许可成功-->Mock服务
    m启动检查--2.License许可请求-->License管理
    Mock服务--4.上报swagger接口数据-->接口文档管理
    h启动检查--License许可请求-->License管理
    Http测试服务--上报测试结果-->测试结果管理
    b启动检查--License许可请求-->License管理
    BDD测试服务--上报测试结果-->测试结果管理
    消息推送-->消息接收
{{< /mermaid >}}

# 相关链接


- [Http Runner](/docs/meter/http-runner)
- [Mock Runner](/docs/meter/mock-runner)