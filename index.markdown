---
layout: home
title: 首页
nav_order: 1
description: 该平台是深圳市大数据研究院政企大数据实验室开发的基于Python语言的基金数据分析工具箱，包含数据管理、行业描述性统计、基金业绩归因、基金经理能力评估等多个模块，目的是研究我国公募基金行业的重大问题。
---



# 基金研究平台
{: .fs-10 }

该平台是深圳市大数据研究院政企大数据实验室开发的基于Python语言的基金数据分析工具箱，包含数据管理、行业描述性统计、基金业绩归因、基金经理能力评估等多个模块，目的是为研究我国公募基金行业的重大问题提供分析工具。
{: .fs-4 .fw-300 }

[模块介绍](#模块介绍){:.bin .btn-primary .fs-4 .mb-2 .mb-md-0 .mr-2}[GitHub](https://github.com/sribd-kaizhang/mutualfund)

---

## 模块介绍
{:.fs-7}

### 数据管理 `data_mgt`
{:.fs-5.5}
该模块主要支持通过WindPy API批量下载与存储基金基本信息与业绩表现数据。在更新数据业绩时序数据时，模块内的函数将自动参考基金类型选择合适的数据对齐与合并方式。同时，基金经理业绩数据将通过合并其管理所有产品的收益序列数据产生。除此之外，为实现对基金业绩的归因分析，模块也支持下载与存储A股市场股票行情数据与经典因子模型数据。

### 行业发展研究 `descr_stat`
{:.fs-5.5}
该模块提供描述性统计方法从公募基金的数量、资产管理规模、基金分类以及基金费率等维度分析公募基金行业的发展。

### 基金业绩评估 `fund_analyzer`
{:.fs-5.5}
该模块提供统计模型与方法帮助从多个角度对基金与基金经理的业绩表现进行评估，包括但不限于绝对收益与风险调整后收益的计算，选股能力与择时能力分析，以及基金业绩持续性的评估。