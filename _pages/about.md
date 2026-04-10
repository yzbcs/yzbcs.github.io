---
permalink: /
title: "Home"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<!-- 主页内容：所有模块整合在一个页面，通过锚点跳转 -->

## About Me

我是于宗伯，2026届本科生。

**研究兴趣**:
- LLM
- agent

---

## News {: #news }

| 日期 | 动态 |
|------|------|
| 2026-04 | 更新个人主页 |
| （请补充） | |

---

## Publications {: #publications }

{% for pub in site.publications %}
- {{ pub.title }} ({{ pub.date | date: "%Y" }})
{% endfor %}

*请编辑 `_publications/` 文件夹添加论文*

---

## Education {: #education }

| 时间 | 学校 | 专业 | 学位 |
|------|------|------|------|
| 2022 - 2026 | （请补充） | （请补充） | 本科 |

---

## Internships {: #internships }

| 时间 | 公司/机构 | 职位 |
|------|-----------|------|
| （请补充） | | |

---

## Study {: #study }

每日推送归档，请点击导航栏的 [Study](/study/) 查看。
