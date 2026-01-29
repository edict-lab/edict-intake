# EDICT-Rho Protocol (EDRP)
## Evidence-based Mathematical Decision Engine / 증거기반 수학적 판정 엔진

**EN**  
EDRP collects verifiable **receipts** (evidence), performs reproducible mathematical decisions against formal conformance rules, and ships signed **labels (label.json)** + **registry snapshots** for audit-ready distribution.

**KR**  
EDRP는 검증 가능한 **증거(Receipt)** 를 수집해 표준/체크리스트에 따라 **재현 가능한 수학적 판정**을 수행하고, 결과를 **서명된 라벨(label.json) + 레지스트리 스냅샷**으로 남겨 유통·감사·조달에 바로 쓰게 하는 절차적 검증 인프라입니다.

---

## High-impact use cases / 적용 예시
- **AI/ML Governance**: model/data/training/deployment conformance, reproducibility, audit evidence
- **Finance / Risk**: model validation evidence, internal controls, timepoint snapshots for approvals
- **Software Supply Chain / Procurement**: build/release/docs conformance labels for third-party verification
- **Regulated domains (healthcare/manufacturing/IoT)**: evidence → decision → label packaging for submissions

---

## Quick submit (30 seconds) / 30초 제출
1) **Issues → New issue**
2) Choose a template: **PoC / Certification / Partner**
3) (Optional) Paste `label.json` as a fenced code block:

```json
{ "example": true }

Security / 보안

Do NOT upload private keys / tokens / customer data.

민감 자료는 요청 시 별도 안전 채널로 안내합니다.
What happens next / 이후 흐름

Intake → auto labeling/check → internal ticket (edict-kit) → tracked in EDRP Leads


---

# 2단계: “3문항을 템플릿에 필수로” 넣기 = 어디에 넣는 건가?

**이슈 템플릿(폼)은 repo 안의 파일**로 관리돼. 위치는 여기:

- `edict-intake/.github/ISSUE_TEMPLATE/` 폴더 안
  - `poc_request.yml`
  - `cert_request.yml`
  - `partner_request.yml`

“필수”는 YAML 안에서 이렇게 쓰는 거야:
```yaml
validations:
  required: true
