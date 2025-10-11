---
theme: seriph
class: text-left
transition: fade-out
background: https://cover.sli.dev
fonts:
  sans: 'Noto Sans SC'
  mono: 'Fira Code'
colorSchema: auto
title: NocoDB 内网工具分享
info: |
  内部分享 · 2025-09-28
seoMeta: {}
download: false
---

# NocoDB

智能数据表工具使用分享

<!-- <div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  结合芯片验证场景，让测试表格、BugList、ChangeList 集中且可追溯，助力验证流程提效 <carbon:arrow-right />
</div> -->

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/Freedyool/sharing" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

---

# 目录

<Toc minDepth="1" maxDepth="1" />

---

# NocoDB：Airtable 的开源替代品

将 MySQL、PostgreSQL、SQLite 转换为智能电子表格。

<img src="/nocodb-arch.png" alt="NocoDB 架构示意" class="mx-auto w-4/5" />

---
layout: two-cols-header
---

# NocoDB 基本概念

::left ::

- field（字段）：表格的列名
- record（记录）：表格的数据行
- base（项目）：若干张表格的集合
- table（表格）：用于数据存储的容器
- view（视图）：用于数据可视化的交互媒介

::right::

```mermaid
graph LR
  B[base] -->|1..n| T1[table]
  B -->|1..n| T2[table]
  T1 -->|1..n| V1[view]
  T1 --> V2[view]
  T2 -->|1..n| V3[view]
  T2 --> V4[view]
```

---

# NocoDB 视图创建

内置 Grid/Kanban/Gallery/Form/Calendar 五种视图

<img src="/nocodb-views.png" alt="NocoDB 视图类型" class="mx-auto w-4/5" />

---

# NocoDB 权限管理

- 系统权限：组织浏览者 / 组织创建者
- 项目权限：所有者 / 创建者 / 编辑者 / 评论者 / 浏览者和无访问权限

<img src="/nocodb-privilege.png" alt="NocoDB 视图类型" class="mx-auto w-3/4" />


---

## NocoDB 项目权限

权限速览表

| 角色 | 浏览数据 | 添加评论 | 编辑数据 | 编辑视图 | 锁定视图 | 编辑字段 | 创建表格 | 管理权限 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 所有者 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| 创建者 | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ❌ |
| 编辑者 | ✔ | ✔ | ✔ | ✔ | ❌ | ❌ | ❌ | ❌ |
| 评论者 | ✔ | ✔ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| 浏览者 | ✔ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

---

# 案例：BK7239N 芯片验证流程

让测试表格、BugList、ChangeList 集中串联，助力验证流程提效

<div class="w-full flex flex-col items-center justify-center">
  <div grid="~ cols-2 gap-4" m="t-4">
    <figure class="text-center">
      <a href="/BK7239N Overview.png" target="_blank" title="7239N芯片验证">
        <img src="/BK7239N Overview.png" alt="7239N芯片验证" class="w-100 h-60 object-cover border rounded shadow-sm" />
      </a>
      <figcaption class="text-xs mt-1 opacity-70">7239N芯片验证</figcaption>
    </figure>
    <figure class="text-center">
      <a href="/BK7239N Relation Chain.png" target="_blank" title="7239N数据表关联">
        <img src="/BK7239N Relation Chain.png" alt="7239N数据表关联" class="w-100 h-60 object-cover border rounded shadow-sm" />
      </a>
      <figcaption class="text-xs mt-1 opacity-70">7239N数据表关联</figcaption>
    </figure>
  </div>
  <div class="mt-2 text-xs opacity-50 text-center">* 缩略图尺寸裁剪显示，点击查看原始清晰度 *</div>
</div>

---
layout: end
---

# 问题反馈与现场讨论

- 关于使用问题：可将问题填写在 README 项目的问题反馈表中
- 关于访问性问题：如遇浏览器报 500，可尝试找 IT 升级浏览器
