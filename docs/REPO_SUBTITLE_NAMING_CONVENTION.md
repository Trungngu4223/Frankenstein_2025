[中文](#本仓库内字幕文件命名规范) | [English](#subtitle-filename-conventions-for-this-repository)

---

# 本仓库内字幕文件命名规范

为便于机器自动化处理本仓库中各个字幕文件（格式转换与发布打包），特约定如下命名与格式规范。本规范仅适用于本仓库，由社区协作与持续修订。

## 总览
推荐格式：`<resolution>.<feature>.<source>.<lang>.<ext>`（全部小写，使用点号`.`分隔）  
示例：`2160p.hdr.amzn.chs-eng.srt`、`2160p.en.srt`

字段说明：
- resolution：分辨率（如 `1080p`、`2160p`）。  
- feature（可选）：特性，如 `hdr`、`dv`、`extended`、`directorcut` 等；若无则省略。  
- source（可选）：来源缩写（仓库统一小写；同分辨率不同时间轴请加来源以区分）。  
- lang：语言/布局代码，必须使用仓库约定的简短代码（全部小写）。示例约定：
  - 单语：`en`、`fr`、`ja` 等。  
  - 中文变体：`chs`（简体）、`cht`（繁体）。  
  - 双语布局/上下顺序：`chs-eng`（中上英下）、`eng-chs`（英上中下）、`cht-eng` 等。  
- ext：文件扩展名（例如 `srt`、`ass`）。

## 数字发行来源缩写
| 缩写 | 平台 / 来源 |
|------|-------------|
| amzn | Amazon / Prime Video |
| dsnp | Disney+ |
| ma   | Max（原 HBO Max） |
| aptv | Apple TV / iTunes |
| nf   | Netflix |
| it   | iTunes |

## 实体发行来源缩写
| 缩写 | 说明 |
|------|------|
| bluray-us | Blu-ray（Region A / US） |
| bluray-eu | Blu-ray（Region B / EU） |
| bluray-jp | Blu-ray（JP / Region-specific） |
| bd25 | Blu-ray 25GB |
| bd50 | Blu-ray 50GB |
| remux | Remux（高清翻轨） |

## 示例文件名
- `1080p.chs.srt` — 仅简体中文字幕  
- `1080p.amzn.chs.srt` — 来自 Amazon 的简体中文字幕  
- `1080p.hdr.it.chs-eng.srt` — 来自 iTunes，包含 HDR，中上英下  
- `2160p.nf.eng-chs.srt` — 来自 Netflix，英上中下布局  
- `1080p.en.srt` — 英语单语字幕  
- `1080p.hdr.it.en.srt` — 来自 iTunes 的 HDR 英文字幕  
- `1080p.bluray-us.cht-eng.ass` — 来自美区 Blu-ray 的繁体/英文 ASS 特效字幕  
- `2160p.remux.en.srt` — Remux 来源的英文字幕

## 注意事项（校验清单）
- 始终使用小写与统一分隔符（`.`）。  
- lang 字段应使用仓库约定的语言/布局代码，便于自动化解析与筛选。  
- 同分辨率不同时间轴请加来源或发行方标识以区分；若同一时间轴下仅有轻微版本差异可省略 feature/source 字段。  
- 当新增语言或新增来源类型时，请在本规范补充对应缩写与说明，确保自动化脚本兼容。

## 兼容性与扩展
- 本规范为仓库级约定，面向多语言、多来源与多格式场景。新增语言、布局或来源类型时，应补充缩写表与示例，并更新自动化脚本以保证解析一致性。



---

# Subtitle filename conventions for this repository

These rules standardize how subtitle files in this repository are named so they can be processed automatically (format conversions, packaging, releases, etc.). This convention applies only to this repository and may be updated by the community as needed.

## Overview
Recommended format: `<resolution>.<feature>.<source>.<lang>.<ext>` (all lowercase, dot-separated)  
Examples: `2160p.hdr.amzn.chs-eng.srt`, `2160p.en.srt`

Field definitions:
- resolution: video resolution (e.g., `1080p`, `2160p`).  
- feature (optional): special attributes such as `hdr`, `dv` (Dolby Vision), `extended`, `directorcut`, etc. Omit if not applicable.  
- source (optional): source/distributor abbreviation (repository uses lowercase). Add this when the same resolution has different timelines to distinguish files.  
- lang: language or layout code — use the repository’s short codes (all lowercase). Examples:
  - Single language: `en`, `fr`, `ja`, etc.  
  - Chinese variants: `chs` (Simplified), `cht` (Traditional).  
  - Bilingual layouts/order: `chs-eng` (Chinese above, English below), `eng-chs` (English above, Chinese below), `cht-eng`, etc.  
- ext: file extension (e.g., `srt`, `ass`).

## Digital release source abbreviations
| Abbrev | Platform / source |
|--------|-------------------|
| amzn   | Amazon / Prime Video |
| dsnp   | Disney+ |
| ma     | Max (formerly HBO Max) |
| aptv   | Apple TV / iTunes |
| nf     | Netflix |
| it     | iTunes |

## Physical release source abbreviations
| Abbrev     | Description |
|------------|-------------|
| bluray-us  | Blu-ray (Region A / US) |
| bluray-eu  | Blu-ray (Region B / EU) |
| bluray-jp  | Blu-ray (Japan / region-specific) |
| bd25       | Blu-ray 25GB disc |
| bd50       | Blu-ray 50GB disc |
| remux      | Remux (lossless/HD rip) |

## Example filenames
- `1080p.chs.srt` — Simplified Chinese only  
- `1080p.amzn.chs.srt` — Simplified Chinese from Amazon  
- `1080p.hdr.it.chs-eng.srt` — iTunes HDR, Chinese above / English below  
- `2160p.nf.eng-chs.srt` — Netflix, English above / Chinese below  
- `1080p.en.srt` — English only  
- `1080p.hdr.it.en.srt` — iTunes HDR English subtitles  
- `1080p.bluray-us.cht-eng.ass` — US Blu-ray, Traditional Chinese + English, ASS style subtitles  
- `2160p.remux.en.srt` — Remux source English subtitles

## Checklist / notes
- Always use lowercase and the dot (`.`) as the separator.  
- Use the repository’s language/layout codes for the lang field to make automated parsing and filtering reliable.  
- If the same resolution has different timelines, include a source or distributor identifier to distinguish files. If multiple files share an identical timeline and only differ in minor ways, the feature/source fields may be omitted.  
- When adding a new language or source type, add its abbreviation and an example to this spec so automation scripts remain compatible.

## Compatibility & extension
This convention is a repository-level standard designed for multilingual, multi-source, multi-format workflows. When introducing new languages, layouts, or source types, update the abbreviation tables and examples and adjust automation scripts to ensure consistent parsing.


---

<div align="center">

**蒙太奇字幕组 (MontageSubs)**  
“用爱发电 ❤️ Powered by love”

</div>


