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

## 원자료 변수 명명 (Source-file variable dictionary)

원자료 측정기록지의 컬럼명 규칙. 분석 코드(`COLMAP`)는 **한글명과 영문 약어를 모두 인식**하므로 어느 표기로 된 파일이든 동일하게 처리된다.

**약어:** `BR` before ROM(사전 가동범위) · `AR` after ROM(사후) · `F` flexion(굽힘) · `E` extension(폄) · `LF` lateral flexion(가쪽굽힘) · `ER` rotation(돌림)¹ · `R/L` right/left.

| 영문 약어 | 한글 원자료 컬럼 | 분석 변수명 | 의미 |
|---|---|---|---|
| Group | 그룹 | group | 군 (1=실험 AI / 2=대조 표준) |
| Sex | 성별 | sex | 성별 |
| Height² | 키(cm) | height | 신장 (cm) |
| Weight | 몸무게(kg) | weight | 체중 (kg) |
| Smartphone | 스마트폰사용시간(시) | smartphone_h | 1일 스마트폰 사용시간 |
| VAS | VAS | VAS | 통증 (0–10) |
| BRF / ARF | BR굽힘 / AR굽힘 | flex_pre / flex_post | 굴곡 (°) 사전/사후 |
| BRE / ARE | BR폄 / AR폄 | ext_pre / ext_post | 신전 (°) 사전/사후 |
| BRLF_R / ARLF_R | BR가쪽굽힘(우) / AR가쪽굽힘(우) | latflexR_pre / latflexR_post | 우측 측방굴곡 (°) |
| BRLF_L / ARLF_L | BR가쪽굽힘(좌) / AR가쪽굽힘(좌) | latflexL_pre / latflexL_post | 좌측 측방굴곡 (°) |
| BRER_R / ARER_R | BR가쪽돌림(우) / AR가쪽돌림(우) | rotR_pre / rotR_post | 우측 회전 (°) |
| BRER_L / ARER_L | BR가쪽돌림(좌) / AR가쪽돌림(좌) | rotL_pre / rotL_post | 좌측 회전 (°) |
| B_CVA1 / A_CVA2³ | B_CVA1 / A_CVA2 | CVA_pre / CVA_post | 두개척추각 (°) 사전/사후 |

¹ 변수 약어상 `ER`(external rotation)로 표기하나, **경부(목) 가동범위에서는 해부학적으로 회전(cervical rotation)을 의미**하며 논문 본문·표·그림에는 "Rotation(회전)"으로 보고한다(external rotation은 어깨·고관절 용어).
² 입력 표기 "Hight"는 "Height"의 오기로 보아 height로 매핑한다(코드는 두 철자 모두 인식).
³ CVA는 변수 레전드에 영문 약어가 제시되지 않아 현행 `B_CVA1`(사전)/`A_CVA2`(사후)를 유지한다. 필요 시 `BCVA1/ACVA2` 등으로 통일 가능하며 코드는 두 표기 모두 인식한다.
