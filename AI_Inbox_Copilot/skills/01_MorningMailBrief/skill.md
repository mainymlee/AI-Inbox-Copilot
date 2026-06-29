---
name: morning-mail-brief
description: 여러 Mail Skill의 결과를 종합하여 하루를 시작하기 전에 확인해야 하는 Morning Mail Brief를 생성할 때 사용하는 Skill이다.
---

## 목적 및 범위

Mail Skill들의 분석 결과를 종합하여
Morning Mail Brief를 Markdown 파일로 생성한다.

결과물

- ## 오늘의 메일 현황
- ## 중요 메일 TOP3
- ## 오늘 일정
- ## 답장이 필요한 메일
- ## 피싱 의심 메일
- ## 뉴스레터 및 광고
- ## Inbox Health Score
- ## 오늘 해야 할 일

총 8개의 섹션으로 구성된 `.md` 파일

---
## 작업 절차

1. spec.md에서 목표, 출력 형식, 성공 기준을 읽는다.
2. Mail Summary Skill 결과를 읽는다.
3. Mail Classification Skill 결과를 읽는다.
4. Priority Analysis Skill 결과를 읽는다.
5. Security Check Skill 결과를 읽는다.
6. Unread Mail Digest Skill 결과를 읽는다.
7. Newsletter Manager Skill 결과를 읽는다.
8. Safe Archive Skill 결과를 읽는다.
9. Action Recommendation Skill 결과를 읽는다.
10. Priority Analysis 결과를 기준으로 중요 메일 TOP3를 선정한다.
11. Security Check 결과에서 HIGH 또는 CRITICAL 메일을 피싱 의심 메일로 표시한다.
12. Unread Mail Digest 결과를 기준으로 읽지 않은 중요 메일을 표시한다.
13. Newsletter Manager 결과를 기준으로 뉴스레터/광고 현황을 요약한다.
14. Action Recommendation 결과를 기준으로 오늘 해야 할 일을 체크리스트로 작성한다.
15. Safe Archive 결과를 기준으로 삭제가 아닌 보관 정책을 반영한다.
16. Inbox Health Score를 계산한다.
17. Morning Mail Brief를 Markdown 형식으로 작성한다.
18. 다음 Skill이 사용할 수 있도록 "다음 Skill 전달 정보" 섹션을 작성한다.
19. 정보가 불확실한 경우 "확인 필요"로 표시한다.
20. 성공 기준과 결과물을 비교하여 누락된 항목이 없는지 확인한다.
---

## 사용 규칙 및 제약 사항

- 메일 원문을 그대로 출력하지 않는다.
- 모든 메일은 핵심만 요약한다.
- 중요도는 이유와 함께 작성한다.
- 피싱 메일은 경고 문구를 반드시 포함한다.
- Safe Archive 정책을 변경하지 않는다.
- Action Recommendation 결과를 그대로 반영한다.
- Markdown 형식을 유지한다.
- 사용자가 30초 안에 이해할 수 있도록 작성한다.

---

## 템플릿

```markdown
# 🌅 Morning Mail Brief

## 📬 오늘의 메일 현황

- 총 메일:
- 읽지 않은 메일:
- 중요 메일:
- 광고 메일:

---

## 🔥 중요 메일 TOP3

### 1.

- 발신자:
- 제목:
- 중요도:
- 이유:
- 해야 할 일:

### 2.

...

### 3.

...

---

## 📅 오늘 일정

- 일정:
- 시간:

---

## ✉️ 답장이 필요한 메일

- 발신자:
- 이유:

---

## ⚠️ 피싱 의심 메일

- 위험도:
- 위험 요소:
- 추천 행동:

---

## 📰 뉴스레터 및 광고

- 뉴스레터:
- 광고 메일:
- 추천 관리 방법:

---

## ❤️ Inbox Health Score

- 점수:
- 상태:
- 감점 요인:
  - 읽지 않은 중요 메일:
  - 답장 필요한 메일:
  - 오늘 마감 메일:
  - 피싱 의심 메일:
  - 장기간 미확인 뉴스레터:

---

## ✅ 오늘 해야 할 일

- [ ] 
- [ ] 
- [ ] 

---

## 다음 Skill 전달 정보

- morning_brief_summary:
- important_mail_count:
- phishing_suspected_count:
- unread_important_count:
- action_items_count:
- inbox_health_score:
- inbox_health_status:
- user_confirmation_required:

---