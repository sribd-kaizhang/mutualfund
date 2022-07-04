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

* 函数：`count_summ(basic_info, end_year = '2021')`

* 描述：根据基金基本资料信息（`basic_info`），计算从1998年至指定结束年份（`end_year`）之间每年新成立、停止运营以及继续运营的公募基金数量。该分析不考虑产品异常状态（如发行失败、暂停募集等）的基金。

* 参数：

  * `basic_info`: _pd.DataFrame_

    基金基本信息，要求至少包含基金代码（_FUND_CODE_）、基金成立日期（_FUND_SETUPDATE_）、到期日期（_FUND_MATURITYDATE_2_）等字段，其中重要日期字段要求数据类型为_Timestamp_。
    
  * `end_year`: _str, default '2021'_
  
    计数考虑的最后年份。