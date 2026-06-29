# 📬 AI Inbox Copilot

> **An Intelligent Email Assistant for Daily Life & Work**

AI Inbox Copilot은 **Gmail과 연동하여 이메일을 분석하고**, 여러 AI Skill을 협업시켜 **중요 메일 분석, 피싱 탐지, 뉴스레터 관리, 안전한 보관 정책 제안, 행동 추천 및 Morning Mail Brief 생성**을 수행하는 AI Agent입니다.

---

# 📌 Overview

이메일에는 학교, 업무, 금융, 배송, 광고, 뉴스레터 등 다양한 메일이 혼재되어 있습니다.

사용자는

- 중요한 메일을 놓치는 문제
- 광고 및 뉴스레터로 인한 메일함 혼잡
- 피싱 메일 구분의 어려움
- 읽지 않은 메일 누적

등을 자주 경험합니다.

AI Inbox Copilot은 이러한 문제를 해결하기 위해 여러 AI Skill을 협업시키는 **Multi-Skill AI Agent**를 구현했습니다.

---

# 🎯 Features

- 📄 이메일 자동 요약 (Mail Summary)
- 🏷 이메일 자동 분류 (Mail Classification)
- ⭐ 중요도 및 긴급도 분석 (Priority Analysis)
- 🛡 피싱·스팸·사칭 위험 분석 (Security Check)
- 📬 읽지 않은 중요 메일 분석 (Unread Mail Digest)
- 📰 뉴스레터 및 광고 메일 관리 (Newsletter Manager)
- 📦 안전한 메일 보관 정책 추천 (Safe Archive)
- ✅ 사용자 행동 추천 (Action Recommendation)
- 🌅 Morning Mail Brief 생성

---

# 🏗 System Architecture

> architecture.png 추가 예정

```
Gmail Connector
        │
        ▼
 AI Inbox Copilot (Agent)
        │
        ├───────────────┐
        ▼               │
 Mail Summary           │
        ▼               │
 Mail Classification    │
        ▼               │
 Priority Analysis      │
        ▼               │
 Security Check         │
        ▼               │
 Unread Mail Digest     │
        ▼               │
 Newsletter Manager     │
        ▼               │
 Safe Archive           │
        ▼               │
 Action Recommendation  │
        ▼               │
 Morning Mail Brief ◀───┘
        │
        ▼
      User
```

---

# 🔄 Workflow

```
New Email

      │

      ▼

Mail Summary

      ▼

Mail Classification

      ▼

Priority Analysis

      ▼

Security Check

      ▼

Unread Mail Digest

      ▼

Newsletter Manager

      ▼

Safe Archive

      ▼

Action Recommendation

      ▼

Morning Mail Brief

      ▼

User
```

---

# 🤖 AI Skills

| Skill | Description |
|--------|-------------|
| Morning Mail Brief | Generate the final daily email briefing |
| Mail Summary | Summarize email content |
| Mail Classification | Categorize emails |
| Priority Analysis | Analyze priority and urgency |
| Security Check | Detect phishing, spam, spoofing, malicious links |
| Unread Mail Digest | Analyze unread important emails |
| Newsletter Manager | Organize newsletters and promotional emails |
| Safe Archive | Recommend safe archive policy |
| Action Recommendation | Recommend next actions for the user |

---

# ⭐ Priority Analysis

Priority Analysis calculates the importance of each email using a scoring rule.

### Example Scoring

| Condition | Score |
|-----------|------:|
| Deadline today | +3 |
| Reply required | +2 |
| School/Work email | +2 |
| Important sender | +2 |
| Financial/Security email | +2 |
| Advertisement | -2 |
| Newsletter | -1 |

Priority Score is normalized to **1~5**.

---

# 🛡 Security Check

Security Check analyzes phishing risk using multiple indicators.

### Risk Factors

- Suspicious sender
- Urgent wording
- Password request
- Personal information request
- Payment request
- Suspicious URL
- Dangerous attachment
- Organization impersonation

### Risk Level

| Score | Level |
|-------:|-------|
| 0~19 | SAFE |
| 20~39 | LOW |
| 40~59 | MEDIUM |
| 60~79 | HIGH |
| 80~100 | CRITICAL |

---

# 📦 Safe Archive Policy

Unlike traditional email assistants,

AI Inbox Copilot **never deletes emails automatically**.

Instead, it recommends a safe archive policy.

| Email Type | Recommended Folder | Retention |
|------------|-------------------|----------:|
| Important Email | Inbox | Keep |
| Phishing Suspected | Risk Mailbox | 30 Days |
| Newsletter | Newsletter Folder | 30 Days |
| Advertisement | Promotion Folder | 14 Days |
| Uncertain Email | Review Folder | 7 Days |

---

# ❤️ Inbox Health Score

The agent calculates an Inbox Health Score to summarize the overall condition of the user's mailbox.

### Deduction Rules

| Condition | Score |
|-----------|------:|
| Unread important email | -10 |
| Reply required | -10 |
| Deadline today | -15 |
| Phishing suspected | -20 |
| Old newsletters | -5 |

Score Range

| Score | Status |
|-------:|--------|
| 90~100 | Excellent |
| 70~89 | Good |
| 50~69 | Warning |
| 30~49 | Needs Cleanup |
| 0~29 | Critical |

---

# 💻 Tech Stack

- Timely AI
- Gmail Connector
- Claude Haiku 4.5
- Markdown Skills
- AI Agent Workflow

---

# 📁 Project Structure

```
AI-Inbox-Copilot/

├── README.md
│
├── agent/
│   ├── agent_prompt.md
│   └── workflow.md
│
├── skills/
│   ├── 01_MorningMailBrief/
│   ├── 02_MailSummary/
│   ├── 03_MailClassification/
│   ├── 04_PriorityAnalysis/
│   ├── 05_SecurityCheck/
│   ├── 06_UnreadMailDigest/
│   ├── 07_NewsletterManager/
│   ├── 08_SafeArchive/
│   └── 09_ActionRecommendation/
│
├── docs/
│   ├── architecture.png
│   ├── workflow.png
│   └── demo.md
│
└── examples/
    ├── sample_email.md
    ├── morning_mail_brief.md
    └── security_report.md
```

---

# 🚀 Future Work

- Gmail automation
- Google Calendar integration
- Reply draft generation
- Smart notification system
- Multi-language support
- Personalized learning based on user behavior

---

# 👨‍💻 Contributors

Team Project for Harness Engineering: AI Agent & Skill Hackathon

Developed with Timely AI
