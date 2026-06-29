---

name: security-check
description: 이메일의 보안 위험도를 분석하여 피싱, 스팸, 사칭, 악성 링크 및 첨부파일 위험성을 판단할 때 사용하는 Skill이다.

---

## 목적 및 범위

Mail Summary, Mail Classification, Priority Analysis의 분석 결과를 기반으로 이메일의 보안 위험도를 분석한다.

결과물

* ## 메일 정보
* ## 보안 위험도
* ## 위험 요소 분석
* ## 피싱 가능성
* ## 추천 행동

5개 섹션으로 구성된 `.md` 파일

---

## 작업 절차

1. spec.md에서 목표, 출력 형식, 성공 기준을 읽는다.
2. Mail Summary Skill 결과를 읽는다.
3. Mail Classification Skill 결과를 읽는다.
4. Priority Analysis Skill 결과를 읽는다.
5. 메일 제목과 본문을 분석한다.
6. 다음 항목을 기준으로 위험 요소를 확인한다.
   - 발신자 신뢰도
   - 긴급성을 유도하는 표현
   - 개인정보 요구
   - 비밀번호 변경 요구
   - 결제 또는 송금 요청
   - 의심스러운 링크
   - 위험한 첨부파일
   - 기관 또는 기업 사칭 여부
   - 문법적으로 어색한 표현
   - 과도한 혜택 또는 당첨 안내
7. 보안 위험도 기준에 따라 Security Score를 계산한다.
8. 최종 Security Score를 0~100 범위로 보정한다.
9. Security Score에 따라 Risk Level을 SAFE, LOW, MEDIUM, HIGH, CRITICAL 중 하나로 분류한다.
10. 피싱 가능성을 낮음, 중간, 높음으로 판단한다.
11. 사용자가 취해야 할 추천 행동을 작성한다.
12. 다음 Skill이 사용할 수 있도록 "다음 Skill 전달 정보" 섹션을 작성한다.
13. 정보가 불확실한 경우 "확인 필요"로 표시한다.
14. 성공 기준과 결과물을 비교하여 누락된 항목이 없는지 확인한다.

## 사용 규칙 및 제약 사항

* 위험도는 반드시 0~100%로 표시한다.
* 피싱 여부를 단정하지 않는다.
* 위험 요소를 반드시 설명한다.
* 링크나 첨부파일이 의심되면 클릭 또는 실행하지 말 것을 안내한다.
* 메일 삭제나 격리는 수행하지 않는다.
* SafeArchive Skill이 활용할 수 있도록 명확한 결과를 제공한다.
* Markdown 형식을 유지한다.
- Security Score는 반드시 보안 위험도 기준을 적용하여 계산한다.
- 최종 Security Score는 0~100 범위로 보정한다.
- Security Score에 따라 Risk Level을 SAFE, LOW, MEDIUM, HIGH, CRITICAL 중 하나로 표시한다.
- HIGH 이상인 경우 링크 클릭 금지와 첨부파일 실행 주의 문구를 반드시 포함한다.
- CRITICAL인 경우 Safe Archive Skill에서 위험 메일함 격리 대상으로 사용할 수 있도록 명확히 표시한다.
---

## 템플릿

```markdown
# 🛡 Security Check

## 메일 정보

- 발신자:
- 제목:
- 수신 시간:

---

## 보안 위험도

- 기본 점수: 0
- 가산/감점 조건:
  - 의심스러운 발신자 주소: +20
  - 긴급성 유도 표현: +15
  - 단축 URL 포함: +15
  - 공식 도메인 확인 가능: 해당 없음
- 최종 Security Score: 50%
- Risk Level: MEDIUM

---

## 위험 요소 분석

- 긴급성을 유도하는 표현 사용
- 단축 URL 포함
- 개인정보 입력 요구
- 공식 기관 사칭 가능성

---

## 피싱 가능성

**높음**

---

## 추천 행동

- 링크를 클릭하지 않는다.
- 첨부파일을 실행하지 않는다.
- 공식 홈페이지에서 직접 확인한다.
- Safe Archive 검토를 권장한다.

## 다음 Skill 전달 정보

- security_score: 50
- risk_level: MEDIUM
- phishing_probability: 중간
- suspicious_sender: 확인 필요
- suspicious_link: true
- suspicious_attachment: 확인 필요
- recommended_security_action: 공식 홈페이지에서 직접 확인
- safe_archive_target: 검토 필요함
- user_confirmation_required: true
```
