# 데이터 설명 (De-identified)

`fhp_measurements_deidentified.csv` — 본 RCT의 **익명화** 측정 자료.

## 개인정보 보호
원자료에 포함된 **이름·학번·출생년도(개인식별정보)는 모두 제거**되었으며, 다음과 같이 비식별화하였습니다.
- 이름·학번 → 익명 ID(`P01`~)로 대체·삭제
- 출생년도 → 연령(age)으로 변환

## 컬럼
| 컬럼 | 설명 |
|---|---|
| id | 익명 대상자 ID |
| group | experimental_AI(실험군) / control_standard(대조군) |
| sex | M/F |
| age | 연령(세) |
| VAS | 통증(0–10) |
| height_cm, weight_kg | 신장·체중 |
| smartphone_h | 1일 스마트폰 사용시간(시간) |
| flex/ext/latflexR/latflexL/rotR/rotL _pre/_post | 경추 6방향 ROM 사전·사후(°) |
| CVA_pre, CVA_post | 두개척추각 사전·사후(°) |

> 결측: 사전·사후 측정이 모두 없는 6명(각 군 3명)은 NaN. 중재효과 분석은 완전자료 34명 기준.
