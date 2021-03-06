---
layout: page
title: 行业发展研究
nav_order: 3
---


# 行业发展研究
{: .fs-10 }

该模块提供描述性统计方法从公募基金的数量、资产管理规模、基金分类以及基金费率等维度分析公募基金行业的发展。

{: .fs-4 .fw-300 }

---

## 基金数量
{:.fs-7}

### 按运营年份
{:.fs-5.5}

* 函数：`count_by_year(basic_info, end_year = '2021')`

* 描述：根据基金基本资料信息（`basic_info`），计算从1998年至指定结束年份（`end_year`）之间每年新成立、停止运营以及继续运营的公募基金数量。该方法不考虑产品异常状态（如发行失败、暂停募集等）的基金。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、基金成立日期（_FUND_SETUPDATE_）、到期日期（_FUND_MATURITYDATE_2_）等字段，其中重要日期字段要求数据类型为_Timestamp_。
    
  * `end_year`: _str, default '2021'_
  
    计数考虑的最后年份。
    
### 按投资类型
{:.fs-5.5}

* 函数：`count_by_type(basic_info)`

* 描述：根据基金基本资料信息（`basic_info`），计算指定年底不同投资类型的继续运营的公募基金数量。该方法参考Wind公募基金一级与二级分类标准，具体划分结果由`basic_info`中历史投资类型所提供。

* 参数:

	* `basic_info`：_pd.DataFrame_
	
	  基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、历史一级投资类型（_FUND_FIRSTINVESTTYPE_HIST_）、历史二级投资类型（_FUND_INVESTTYPE_HIST_）等字段，其中一级与二级投资类型将决定该统计结果的参照日期。


## 基金规模
{:.fs-7}

### 按运营年份
{:.fs-5.5}

* 函数：`nav_by_year(fund_size, end_year = '2021')`

* 描述：根据描述基金规模的面板数据（`fund_size`），计算不同年份之间每年中国公募基金市场资产管理规模与变化比例。该分析不考虑产品异常状态（如发行失败、暂停募集等）的基金。

* 参数：

  * `fund_size`: _pd.DataFrame_

    基金资产管理规模，数据集要求为以年份为列索引、基金代码为行索引的面板数据。
    
  * `end_year`: _str, default '2021'_
  
    统计考虑的最后年份。

### 按投资类型
{:.fs-5.5}

* 函数：`nav_by_type(basic_info, fund_size, ref_year)`

* 描述：根据基金基本资料信息（`basic_info`）与基金资产管理规模数据（`fund_size`），计算指定年份（`ref_year`）年底继续运营的不同投资类型的公募基金资产管理规模。该方法参考Wind公募基金一级与二级分类标准，具体划分结果由`basic_info`中历史投资类型所提供。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、历史一级投资类型（_FUND_FIRSTINVESTTYPE_HIST_）、历史二级投资类型（_FUND_INVESTTYPE_HIST_）等字段，其中一级与二级投资类型将决定该统计结果的参照日期。

  * `fund_size`: _pd.DataFrame_

    基金资产管理规模，数据集要求为以年份为列索引、基金代码为行索引的面板数据。

  * `ref_year`: _str_

    参考年份，需要与历史投资类型选用的日期一致。

## 基金费率
{:.fs-7}

### 管理费率
{:.fs-5.5}

* 函数：`mgtfee_by_type(basic_info)`

* 描述：根据基金基本信息（`basic_info`），计算指定年份（`ref_year`）年底继续运营的不同投资类型（一级分类）的公募基金管理费率的平均数、最小（大）值与四分位数值。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、历史一级投资类型（_FUND_FIRSTINVESTTYPE_HIST_）、历史管理费率（_FUND_MANAGEMENTFEERATIO2_）等字段，其中历史一级投资类型与历史管理费率将决定该统计结果的参照日期。

### 管理费率（股票型）

{:.fs-5.5}

* 函数：`mgtfee_by_type_stock(basic_info)`

* 描述：根据基金基本信息（`basic_info`），计算指定年份（`ref_year`）年底继续运营的投资类型（二级分类）的股票型公募基金管理费率的平均数、最小（大）值与四分位数值。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、历史二级投资类型（_FUND_INVESTTYPE_HIST_）、历史管理费率（_FUND_MANAGEMENTFEERATIO2_）等字段，其中历史二级投资类型与历史管理费率将决定该统计结果的参照日期。

### 托管费率

{:.fs-5.5}

* 函数：`custfee_by_type(basic_info)`

* 描述：根据基金基本信息（`basic_info`），计算指定年份（`ref_year`）年底继续运营的不同投资类型（一级分类）的公募基金托管费率的平均数、最小（大）值与四分位数值。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，数据集要求至少包含基金代码（_FUND_CODE_）、历史一级投资类型（_FUND_FIRSTINVESTTYPE_HIST_）、历史托管费率（_FUND_CUSTODIANFEERATIO2_）等字段，其中历史一级投资类型与历史托管费率将决定该统计结果的参照日期。
