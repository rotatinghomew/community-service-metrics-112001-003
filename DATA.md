# 社工服务覆盖与结果队列：资料说明

用于观察匿名服务对象从资格纳入、转介、接触到回访的过程，不包含真实身份资料。

每个 JSON 文件均为 UTF-8 编码。空字符串表示来源没有给出该事实，不等同于零、否或业务终态。标识仅在本项目资料内有意义。

## `cohorts.json`

字段：id, service, valid_from, valid_to, followup_days。共 2 条合成记录。

## `people.json`

字段：id, grid_at_entry, eligible_from, eligible_to, exit_reason。共 4 条合成记录。

## `services.json`

字段：id, person, cohort, referred_at, contact_at, status。共 5 条合成记录。

## `followups.json`

字段：id, service, at, result, consent。共 4 条合成记录。

## 关系与口径提示

services.person/cohort 分别对应 people.id/cohorts.id；followups.service 对应 services.id。每项服务按 cohort.followup_days 判断结果观察期。退出、拒绝、未联系和未到观察期均是不同事实。
