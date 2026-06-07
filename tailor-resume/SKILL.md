---
name: tailor-resume
description: Research target companies and job descriptions, inspect a candidate's existing resumes and evidence files, create truthful role-specific Chinese or English resumes, edit DOCX templates without overwriting originals, verify formatting visually, and prepare delivery-ready DOCX/PDF files. Use for resume creation, targeted resume tailoring, internship or job applications, resume audits, experience rewriting, project selection, ATS keyword alignment, DOCX formatting repair, or PDF export.
---

# Tailor Resume

Create evidence-based, role-specific resumes and carry the work through document QA.

## Core Rules

- Never invent experience, metrics, tools, awards, ownership, or proficiency.
- Distinguish `used`, `practiced`, `familiar with`, `understand`, and `interested in`.
- Preserve every source resume and template. Create a new output unless the user explicitly requests an in-place edit.
- Save generated files in the user-designated workspace.
- Follow workspace deletion restrictions. Remove only explicit process files when authorized.
- Use the Documents skill for DOCX creation/editing and its render-inspect-iterate workflow.
- Browse for current company, product, and job information. Prefer official company, careers, regulatory, product, and first-party sources.

## Workflow

1. **Inspect inputs**
   - Locate resumes, templates, photos, transcripts, project reports, code, portfolios, notes, certificates, and job descriptions.
   - Extract the current resume structure and formatting before editing.
   - Read only evidence relevant to the target role.

2. **Research the target**
   - Identify company business, products, customers, terminology, culture, role family, required skills, and preferred evidence.
   - Separate company facts from inference.
   - If an exact JD is unavailable, state the assumed role direction before drafting.
   - Read [references/research.md](references/research.md).

3. **Build an evidence map**
   - Map each role requirement to verified evidence, transferable evidence, or an honest gap.
   - Rank evidence: direct internship > shipped project > competition/research > coursework > self-study > stated interest.
   - Do not turn self-study into professional experience.
   - Read [references/content-strategy.md](references/content-strategy.md).

4. **Choose content**
   - Lead with the most role-relevant evidence, not necessarily the newest.
   - Keep one-page student resumes focused. Remove low-value items before shrinking type.
   - Use project titles that reveal the system and relevant capability.
   - Include visible portfolio URLs when the resume will be exported to PDF.

5. **Write bullets**
   - Use `label: action + object + method + result/impact`.
   - Prefer specific technologies, workflows, scope, and verified outcomes.
   - Avoid unsupported superlatives and vague personality claims.
   - Match JD terminology naturally; do not keyword-stuff.

6. **Create a new DOCX**
   - Copy the chosen source/template to a new target-specific filename.
   - Preserve the established visual system unless the user requests redesign.
   - Apply consistent section, entry, body, label, date, and URL styles.
   - Read [references/docx-quality.md](references/docx-quality.md).

7. **Validate**
   - Run `scripts/audit_resume_docx.py <resume.docx>`.
   - Render the DOCX and inspect every page at readable zoom.
   - Check font consistency, bold scope, section colors, title/date alignment, line wrapping, image placement, placeholders, comments, density, and page count.
   - Iterate until clean.

8. **Deliver**
   - Return the new targeted file only, unless the user requests intermediates.
   - When PDF is requested, prefer a text-selectable converter. If forced to use an image-based PDF fallback, disclose that text is not selectable.
   - Keep the editable DOCX.

## Decision Guidance

- **No exact role supplied:** research likely role families, choose the strongest evidence-backed direction, and name the assumption.
- **Weak direct match:** emphasize transferable evidence and self-study honestly; do not fabricate domain experience.
- **Too much content:** remove weak projects, compress old coursework, then shorten bullets. Do not solve density by using tiny text.
- **Formatting conflict:** follow the user-approved template and explicit feedback over generic design preferences.
- **Date alignment problems:** use one right-aligned tab stop across all entry headings; do not use spaces.
- **Mixed fonts:** set East Asian, ASCII, and high-ANSI font channels explicitly.

## Typical Triggers

- “根据这个岗位帮我改一份简历。”
- “调查这家公司并新建一版简历。”
- “从我的课程文件夹找适合写进简历的项目。”
- “修正简历里的字体、加粗、日期对齐和照片。”
- “把最终简历转换为 PDF。”
