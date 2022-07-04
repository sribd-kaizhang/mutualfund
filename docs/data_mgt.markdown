---
layout: home
title: 数据管理
nav_order: 2
---


# 数据管理
{: .fs-10 }

该模块主要支持通过WindPy API批量下载、存储与更新基金基本信息与业绩表现数据。同时，基金经理业绩数据将通过合并其管理所有产品的收益序列数据产生。除此之外，为实现对基金业绩的归因分析，模块也支持下载与存储A股市场股票行情数据与经典因子模型数据。
{: .fs-4 .fw-300 }

---

## 基金数据
{:.fs-7}

### 基本信息
{:.fs-5.5}

* 函数：`update_fund_perf(fund_updated, fundtype_anytime_date, to_dir = '../data/basic_info', filename)`

* 描述：通过_WindPy API_下载或更新基金基本信息，其中支持获取基金历史一级与二级投资类型。为便于后续分析基金行业发展，每年最后一个交易日的时点数据通常被下载并存储于以其日期结尾的表格文件，如`filename  = 'fund_basic_info_20211231'`。

* 参数：

  * `fund_updated`: _list_

    需要下载数据的基金代码，格式`'999999.OF'`。

  * `fundtype_anytime_date`：_str_

    判断基金投资类型的基准日期，日期格式为`%Y-%m-%d`。

  * `to_dir`: _str_, default `'../data/basic_info'`

    存储基金基本信息文件的目录，支持绝对路径与相对路径。

  * `filename`: _str, default_ `'fund_basic_info'`

    存储基金基本信息的文件名称。 

### 业绩序列
{:.fs-5.5}

- 函数：`update_fund_perf(fund_updated, months_updated, to_dir = '../data/fund_perf')`

- 描述：通过_WindPy API_下载或更新基金收益序列数据，同时各只基金月收益序列将单独地存储于以基金代码命名的表格文件。当执行更新时，函数将识别继续运营基金与新成立基金。对于继续运营基金，新收益序列与历史收益序列合并组成完整的收益序列，并更新到对应表格文件中；对于新成立但非转型基金，将只获取从成立日期至最新的收益数据，并存储于新创建的表格文件；对于新成立且转型基金，将获取从1998年3月至最新的收益数据，并存储于新创建的表格文件。

- 参数：

  - `fund_updated`：_list_

    需要下载或更新数据的基金代码，格式为'999999.OF'。

  - `months_updated`：_list_

    需要下载或更新数据的日期序列，时间格式为`%Y-%m-%d`。

  - `to_dir`：_str, default_ `'../data/fund_perf'`

    存储基金收益序列文件的目录，支持绝对路径与相对路径。