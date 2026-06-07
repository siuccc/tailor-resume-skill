# Tailor Resume Skill

An evidence-first Codex skill for researching target roles, tailoring resumes,
editing DOCX templates, and checking the finished document before delivery.

[中文说明](#中文说明) | [English](#english)

## 中文说明

`tailor-resume` 不只是把经历写得更“好听”。它会先研究目标公司与岗位，
再从候选人的简历、课程项目、代码、报告和证书中建立证据映射，最后生成一份
真实、定向且经过版式检查的简历。

### 核心能力

- 调研目标公司、产品、岗位职责和技能关键词
- 遍历候选人材料，甄别真正适合写入简历的经历
- 区分直接经验、可迁移经验、自学经历和能力缺口
- 根据岗位重排教育、实习、项目、竞赛与技能内容
- 在不捏造经历、指标或熟练度的前提下改写要点
- 保留原文件，创建新的岗位定向 DOCX
- 检查字体、加粗、日期对齐、批注、占位符、图片和可见链接
- 配合文档渲染流程完成视觉检查，并准备 PDF 版本

### 安装

克隆仓库后，将 Skill 目录复制到 Codex skills 目录：

```bash
git clone https://github.com/siuccc/tailor-resume-skill.git
cp -R tailor-resume-skill/tailor-resume ~/.codex/skills/
```

重新启动 Codex 后即可使用：

```text
Use $tailor-resume to research this company and create a targeted resume
without overwriting my original file.
```

也可以直接用中文：

```text
使用 $tailor-resume 调研这家公司，并根据岗位要求新建一份定向中文简历。
不要修改原文件，也不要虚构经历。
```

### DOCX 审计脚本

Skill 附带一个轻量结构审计工具：

```bash
python tailor-resume/scripts/audit_resume_docx.py path/to/resume.docx
python tailor-resume/scripts/audit_resume_docx.py --strict path/to/resume.docx
```

它会检查：

- Word 批注与模板占位符残留
- 显式字体通道是否混杂
- 日期行是否使用统一的右对齐制表位
- 自动编号、图片数量和可见 URL

该脚本需要 Python 3 和 `python-docx`。

### 设计原则

1. **证据优先**：没有材料支持的经历、工具和结果不会被写入。
2. **岗位定向**：内容选择和顺序由目标岗位决定，而不是机械套模板。
3. **原件保护**：默认新建文件，不覆盖候选人的源简历或模板。
4. **交付闭环**：从调研、改写到 DOCX/PDF 检查，而非停在文本建议。

## English

`tailor-resume` is an evidence-first resume workflow for Codex. It researches
the target company and role, maps job requirements to verified candidate
evidence, writes role-specific content, edits a new DOCX without overwriting
the source, and audits the finished document.

### Highlights

- Company and job-description research
- Evidence mapping across resumes, code, reports, coursework, and certificates
- Honest distinction between professional use, project use, practice, and interest
- Role-specific content selection, ordering, and keyword alignment
- DOCX template preservation and formatting guidance
- Structural checks for comments, placeholders, fonts, dates, media, and URLs
- Visual verification and PDF delivery workflow

### Repository Structure

```text
tailor-resume/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── content-strategy.md
│   ├── docx-quality.md
│   └── research.md
└── scripts/audit_resume_docx.py
```

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT License. See [LICENSE](LICENSE).
