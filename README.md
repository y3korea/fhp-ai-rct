# AI 생성 운동 프로그램이 전방머리자세(FHP) 대학생의 두개척추각과 경추 가동범위에 미치는 효과: 무작위대조시험

> Effects of an AI-Generated Exercise Program on Craniovertebral Angle and Cervical Range of Motion in University Students with Forward Head Posture: A Randomized Controlled Trial

경운대학교 물리치료학과 캡스톤 연구 (2026) · 강준환·김강현·김서윤·박지원·오영인·이채은 / 지도교수 최완석

## 개요
전방머리자세(FHP, CVA<50°) 대학생 40명을 **AI 생성 운동군(n=20)** 과 **표준 임상 운동군(n=20)** 에 무작위 배정하여
5주간(주 2회, 회당 20분) 중재 후 두개척추각(CVA)과 경추 6방향 가동범위(CROM)를 비교한 평가자 맹검 RCT.

## 주요 결과 (사전·사후 완전자료 34명)
- CVA 시점 주효과 유의: F(1,32)=125.41, p<.001, partial η²=.80 (양 군 모두 호전)
- **모든 변수에서 군×시점 상호작용 비유의** → AI 운동이 표준 운동과 유사한 효과 (대립가설 기각)
- 동등성 단정은 검정력 한계로 신중 해석 (비열등성 설계 후속연구 필요)

## 저장소 구성
```
fhp-ai-rct/
├── data/        익명화 측정자료(CSV) + 설명  ※ 개인식별정보 제거
├── notebook/    분석 노트북(Colab/로컬, 4셀)
├── paper/       논문(.docx/.pdf/.md) + 그림(PNG)
├── requirements.txt
└── LICENSE
```

## 재현 방법
```bash
pip install -r requirements.txt
# notebook/fhp_rct_analysis.ipynb 실행 (Colab: 런타임▸모두 실행)
```
분석은 2(군)×2(시점) 혼합설계 반복측정 ANOVA(수동 구현 + pingouin 교차검증, 자기검증 항등식 내장).

## 개인정보 보호
원자료의 **이름·학번·출생년도는 제거**되었으며 익명 ID·연령으로 비식별화했습니다.
식별정보가 포함된 원본 엑셀은 `.gitignore`로 저장소에서 영구 제외됩니다.

## 인용
> 강준환, 김강현, 김서윤, 박지원, 오영인, 이채은. AI 생성 운동 프로그램이 전방머리자세 대학생의 두개척추각과 경추 가동범위에 미치는 효과: 무작위대조시험. 경운대학교 물리치료학과, 2026.
