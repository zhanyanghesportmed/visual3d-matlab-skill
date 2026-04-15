# Visual3D-MATLAB Skill 使用说明与能力边界

本文档说明 `visual3d-matlab-integration-workflow-expert` 这个 skill 的用途、使用方法、可实现内容和限制。

## 1. 这个 skill 是做什么的

这是一个面向生物力学实验室流程的 Visual3D-MATLAB 集成技能，目标是：

- 让 Visual3D 与 MATLAB 的联动流程可复现、可审计、可版本管理
- 强制先做架构设计，再分模块输出，降低一次性生成大段代码导致的错误
- 在高风险环节（版本、路径、MAT 结构、DLL 接口）做显式门禁

## 2. 能实现什么

### 2.1 三种官方集成模式

1. `Mode A`：MAT 文件交换（推荐默认）
- Visual3D 导出 `.mat` -> MATLAB 处理 -> 保存 `.mat` -> Visual3D 导入

2. `Mode B`：MATLAB 编译可执行文件（EXE）
- Visual3D 导出 MAT -> 调用 EXE -> EXE 输出 MAT -> Visual3D 导入

3. `Mode C`：DLL 插件模式
- Visual3D 通过插件命令调用 DLL
- 强制要求同时提供：`.dll` + 同名 `.txt` 接口描述文件

### 2.2 工作流能力

- 架构设计输出（不直接跳代码）
- 分模块生成：导出管线、MATLAB 解析、信号处理、保存逻辑、导入管线、EXE 包装、DLL 描述、自动化触发
- 版本风险提示（MATLAB release / 编译器 / 插件兼容）
- 路径与运行风险提示（PATH、绝对路径、Windows 空格路径）
- MAT 结构契约检查（字段、维度、cell 结构、frame-rate 元数据）
- RECALC 持久化与重复定义风险控制

### 2.3 可追溯能力

- 规则到知识库页面映射：`references/kb_rule_to_page_map.md`
- 知识来源与覆盖说明：`references/kb_source_map.md`
- 自动提取报告：`references/generated/kb_extraction_report.md`

## 3. 使用方法

## 3.1 触发方式

在对话里显式调用：

`$visual3d-matlab-integration-workflow-expert`

## 3.2 标准流程（建议严格执行）

1. 先选模式：`A` / `B` / `C`
2. 提供 13 项必填信息（见下一节）
3. 先让 skill 输出“架构设计”（不出代码）
4. 你确认后，按模块逐个生成
5. 每次只生成一个模块，便于验证

## 3.3 13 项必填信息

1. MATLAB version
2. Visual3D version
3. integration mode (`A/B/C`)
4. compiler availability
5. Visual3D 与 MATLAB 安装路径
6. plugin path（`C` 必填，`B` 常用）
7. MAT-file 结构要求
8. 输入 signal names
9. signal folder
10. signal type
11. 输出变量名
12. 是否需要 cell array
13. 是否强制 `-v6`

## 3.4 推荐提示词模板

`Use $visual3d-matlab-integration-workflow-expert. Mode=A. MATLAB=R2023b. Visual3D=6.x. I will provide 13 required fields, then you return architecture only.`

## 4. 关键硬规则（必须遵守）

- DLL 模式必须是 `.dll + 同名 .txt`，不可缺失
- 不允许默认假设 MATLAB 版本、编译器可用性、路径、MAT 字段
- MAT 往返流程中，应明确考虑 `save(...,'-v6')` 兼容策略
- 必须显式 signal mapping，不做隐式映射
- 保留 frame-rate / 文件名元数据 / 缺失值语义
- 先架构后代码；一次一模块

## 5. 典型适用场景

- 实验室批处理流程标准化
- Visual3D 与 MATLAB 的双向数据交换
- 需要可审计、可复现实验记录
- 团队协作中避免“口口相传脚本”导致的流程漂移

## 6. 不适用或需谨慎场景

- 未知 MATLAB release + 未知编译器环境下直接做 DLL/EXE 交付
- 未定义 MAT 契约就要求一次性全流程代码
- 把 RECALC 当作临时调试区而不做持久化影响检查

## 7. 仓库内相关文件

- 技能主定义：`SKILL.md`
- UI 元数据：`agents/openai.yaml`
- 图标资源：`assets/`
- 规则参考：`references/`
- 生成型提取结果：`references/generated/`

## 8. 你可以怎么快速开始

1. 打开 skill，先选 `Mode A`
2. 把你当前项目的 13 项参数贴进去
3. 先确认架构
4. 从 `export pipeline` 模块开始逐步落地
