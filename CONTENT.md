# CONTENT — seongmi98.github.io

콘텐츠 원본. index.html 수정 시 문구는 여기를 기준으로 한다.

## Header

- 이름: 선성미 (Seongmi Seon)
- 직무 정의: 센서·영상 데이터 기반 품질 예측 모델 개발
- 소속: 계약연구원 · 서울대학교 산학협력단 (바이오시스템공학과 생체물성연구실)
- 핵심 수치 3개 (mono):
  - mIoU: +20%p (57.25% → 77.33%)
  - F1: 0.943
  - 추론속도: 1.86×
- 버튼: 이력서 PDF(`assets/resume.pdf`, 아직 파일 없음 — 추후 추가) / 이메일 복사 / GitHub

## 소개 (3~4줄)

센서와 영상 데이터로 대상의 상태를 정량적으로 예측하는 모델을 만든다. RGB·초분광·뎁스 등
서로 다른 성질의 데이터를 다루며 수집 설계부터 전처리, 학습, 검증까지 분석 파이프라인 전
과정을 수행해 왔다. 여러 모델을 비교해 근거를 갖고 하나를 선택하는 일, 그 선택이 실제
운영 환경에서 유지되는지 검증하는 일에 강점이 있다.

## Projects

### P.01 실시간 객체 탐지 모델 비교·선정 및 로봇 시스템 적용
- 기간 / 소속: 2024.01–2024.12 · 국립순천대학교 · 석사 학위논문
- 센서 대역: RGB (가시광)
- 문제: 좁은 간격으로 혼재된 두 대상을 로봇이 실시간으로 구분해야 함
- 접근: 직접 수집·라벨링한 이미지 234장으로 객체 탐지 모델 5종(YOLOv8, YOLOv11, RT-DETR, EfficientDet, Faster R-CNN) 학습·비교
- 결과: 대상 A는 YOLOv11(F1 0.943, mAP@0.5 0.970), 대상 B는 RT-DETR(F1 0.803, mAP@0.5 0.889) 최우수. 추론 속도(RT-DETR 대비 1.86×)를 함께 고려해 YOLOv11을 탑재 모델로 최종 선정, 레이저 제거 로봇 시스템에 적용
- Tags: YOLOv11, RT-DETR, EfficientDet, Faster R-CNN
- Detail: https://github.com/seongmi98 (임시. 개별 repo 만들어지면 그 URL로 교체)

### P.02 항공 RGB 영상 시맨틱 분할 및 학습 전략 최적화
- 기간 / 소속: 2025.03–2025.07 · 서울대학교 생체물성연구실
- 센서 대역: RGB (가시광)
- 문제: 항공 촬영 RGB 영상에서 4종 대상을 픽셀 단위로 구분해야 함. 단일 통합 모델의 한계 확인
- 접근: 대상군을 분리해 학습하는 전략 설계, Mask2Former 기반 분할 모델에 적용. 전국 3개년(2022–2024) 데이터를 시간적으로 분리해 평가 설계 구성, 촬영 고도(10–100m)별 일반화 성능 검증
- 결과: mIoU 57.25% → 77.33% (+20%p) 개선. 저고도(10–30m) 학습이 가장 우수한 일반화 성능
- Tags: Semantic Segmentation, Mask2Former, Temporal Split Validation
- Detail: https://github.com/seongmi98 (임시. 개별 repo 만들어지면 그 URL로 교체)

### P.03 초분광 영상 기반 비파괴 함수율 예측 회귀 모델
- 기간 / 소속: 2025.09–2025.12 · 서울대학교 생체물성연구실
- 센서 대역: Vis-NIR (400–1000nm) · NIR (900–1700nm)
- 문제: 대상을 파괴하지 않고 내부 수분 상태를 정량 예측해야 함
- 접근: Vis-NIR·NIR 초분광 카메라 2종으로 데이터 수집 시스템 구축, 전처리 기법(SNV, MSC, SG, 1·2차 미분) 비교로 최적 파이프라인 도출, PLSR·ANN 회귀 모델을 R²·RMSE 기준 비교 평가
- 결과: SAM2 기반 반자동 스펙트럼 세그멘테이션으로 라벨링 정확도 95% 이상 확보, 라벨링 공정 단축
- Tags: Hyperspectral Imaging, PLSR / ANN, SAM2
- Detail: https://github.com/seongmi98 (임시. 개별 repo 만들어지면 그 URL로 교체)

### P.04 분광·초분광·측색 데이터 기반 복합재 물성 분류·예측 모델 (팀 프로젝트, 축약)
- 기간 / 소속: 2025.07–2025.09 · 서울대학교 생체물성연구실 · 팀 프로젝트
- 센서 대역: Vis-NIR·NIR 초분광 카메라, 분광기, 측색계 (4종 센서)
- 요약: 데이터 수집과 모델 개발 파트로 참여, Vis-NIR·NIR 초분광 카메라·분광기·측색계 4종 센서로 수집한 데이터에 전처리 및 특징 추출 기법 적용
- Tags: Hyperspectral Imaging, Spectroscopy, Colorimetry, Feature Extraction

## Tech Stack (텍스트 목록, 아이콘 없음)

- Python
- PyTorch, YOLOv8/v11, RT-DETR, EfficientDet, Faster R-CNN, Mask2Former, SAM2
- PLSR, ANN, 분광 전처리 (SNV, MSC, Savitzky-Golay, 미분)
- Vis-NIR & NIR 초분광, RGB, Depth 센서
- Git, Autodesk Inventor

## Awards / 수상

- 한국농업기계학회 추계학술대회 우수논문 포스터상 · 2024 · 딥러닝 알고리즘을 이용한 배추 모종 및 잡초 객체 탐지 기술 연구
- 농업용 AI 로봇 응용 및 실습 프로그램 경진대회 장려상 · 2024.07 · 서울대학교 사업단 주관 · ArUco 마커 인식 자율주행 및 YOLOv8 과실 계수 미션
- 한국농업기계학회 추계학술대회 우수논문 포스터상 · 2022 · 케나프 및 목재를 이용한 펠릿 제조 및 연료 특성 분석

## 학회 발표

- [1] Oral · 2025 · 한국농업기계학회 2025 추계학술대회 · 구두 발표
  - KR: 드론 RGB 영상 기반 밭작물 분류를 위한 객체 인식 모델 개발
  - EN: Development of Segmentation Model for Field Crop Classification Based on Drone RGB Imagery
- [2] Poster · 1st Author · 2026 · 한국농업기계학회 2026 춘계학술대회 · 포스터
  - 제목: 분광/초분광 데이터를 활용한 균사체 복합소재 기계적 물성 비파괴 예측 모델 개발
  - 세부: Vis-NIR·SWIR 분광 및 초분광 센서 4종 비교, 회귀 R² 0.78–0.89
- [3] Poster · 1st Author · 2024 · CIGR 2024 (International Commission of Agricultural and Biosystems Engineering) · 포스터
  - 제목(EN): Development of Kimchi Cabbage and Onion Robot Object Detection Model Based on YOLO
  - 세부: YOLO 기반 객체 탐지, 증강 후 데이터셋 6,020장 구축
- [4] Poster · 2023 · 한국농업기계학회 2023 춘계학술대회 · 포스터
  - KR: 반탄화에 의한 케나프와 미사용 목재혼합 펠릿연료의 비교분석
  - EN: Comparative Analysis of Kenaf and Unused Wood Mixed Pellet Fuel by Half-Carbonization

Oral/Poster는 index.html에서 배지 색으로 구분(`badge-oral` 채움 / `badge-poster` 외곽선), 1st Author는 별도 `badge-author`.

## 학력 / 경력 / 자격

- 학력(석사): 농업기계공학과, 국립순천대학교 대학원 · 공학석사 · 2025.02 졸업. 학위논문: 딥러닝 알고리즘을 이용한 객체 탐지 기술 연구
- 학력(학사): 융합바이오시스템기계공학과, 국립순천대학교 · 공학사 · 2023.02 졸업
- 경력: 계약연구원, 서울대학교 산학협력단 (바이오시스템공학과 생체물성연구실) · 2025.03 – 현재 · Seoul, Korea
- 자격: 일반기계기사, 한국산업인력공단 · 2023.12

## Footer / Contact

- Email: ddl05059@naver.com
- GitHub: https://github.com/seongmi98

## 넣지 않는 항목

- 전화번호, 주소, 생년월일
- 방문자 카운터, 다크모드 토글, 언어 전환 버튼
- 기술 스택 아이콘 그리드
- "About Me" 감성 문단 (취미, 좌우명 등)
