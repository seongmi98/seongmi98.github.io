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
- Detail: https://github.com/seongmi98/drone-cropgroup-segmentation

### P.03 초분광 영상 기반 대추 함수율 비파괴 예측
- 기간 / 소속: 2025.09–2025.12 · 서울대학교 생체물성연구실 · 산림청 국가 R&D 과제(임산물 산지종합유통센터 자동화) 서울대 파트
- 센서 대역: Specim FX10 (400–1000nm, VNIR, 224밴드) · KSP-3 (900–1700nm, NIR, 640밴드, 수분 O-H 흡수대 포함)
- 배경: 대추 수분 함량이 저장성·품질 좌우. 기존 측정(오븐건조법 등)은 파괴적이거나 표면 접촉식 — 비파괴 전체표면 측정 필요
- 접근: 카메라 2종 촬영 시스템 구축 → SAM2 반자동 세그멘테이션 → 반사율 추출(Savitzky-Golay 스무딩) → 전처리 기법(SNV, MSC, SG, 1·2차 미분) 비교 → PLSR 회귀 모델 K-Fold 교차검증, R²·RMSE 평가
- 결과: 라벨링 정확도 95% 이상 확보, 라벨링 공정 단축. 원본 데이터·라벨 비공개라 최종 R²/RMSE는 미공개
- 이미지: docs/figures 참고 — reflectance_ksp.png, reflectance_specim.png, preprocessing_comparison_ksp.png, plsr_structure_diagram.png (다운로드해 img/case-studies/jujube/에 저장, 사이트에 삽입 완료)
- Tags: Hyperspectral Imaging, PLSR, SAM2
- Detail: https://github.com/seongmi98/jujube-hsi-moisture
- 스타일 원칙: 프로젝트 상세 페이지는 압축된 문제/접근/결과 대신 배경-데이터수집-라벨링-반사율추출-전처리와모델링-결과 순서의 케이스 스터디 서술(.case-section)로 작성, 실제 이미지가 있으면 .case-image-slot/.case-image-row에 삽입, 없으면 "(추가 예정)" placeholder 유지. 문체는 음슴체(간결体), 실제 공개되지 않은 수치는 지어내지 않음
- Detail: https://github.com/seongmi98 (임시. 개별 repo 만들어지면 그 URL로 교체)

### P.04 분광·초분광·측색 데이터 기반 복합재 물성 분류·예측 모델 (팀 프로젝트, 축약)
- 기간 / 소속: 2025.07–2025.09 · 서울대학교 생체물성연구실 · 팀 프로젝트
- 센서 대역: Vis-NIR·NIR 초분광 카메라, 분광기, 측색계 (4종 센서)
- 요약: 데이터 수집과 모델 개발 파트로 참여, Vis-NIR·NIR 초분광 카메라·분광기·측색계 4종 센서로 수집한 데이터에 전처리 및 특징 추출 기법 적용
- Tags: Hyperspectral Imaging, Spectroscopy, Colorimetry, Feature Extraction

### 기타 (Side Project) — portfolio.html 하단, 메인 4개보다 작은 비중으로 표시

- 대전 공공자전거 '타슈' 대여 데이터 이상치 검증 및 재분석
- 요약: 공공데이터 132만 건 중 '타슈관제센터 정비입고/정비대기'가 실제 대여소가 아니라 자전거 회수·정비 운영 로그임을 발견(평균 이용시간 4배 이상 차이로 검증), 이를 제외하고 인기 대여소·경로 재분석
- Tags: Python, Pandas, EDA, Outlier Detection
- Detail: https://github.com/seongmi98/tashu-bikeshare-data-quality
- 스타일 원칙: 메인 프로젝트 카드(.project-card-plain)와 다른 가벼운 톤(.side-project-row: 대시 보더, 작은 글씨, 지표 강조 없음)으로 표시해 "센서·영상 데이터" 메인 내러티브를 흐리지 않도록 함

## Tech Stack (텍스트 목록, 아이콘 없음)

- Language: Python
- ML/DL: PyTorch · YOLO · OpenCV
- Data: NumPy · Pandas · 분광 데이터 전처리 및 회귀 모델링
- Vision: Object Detection · Semantic Segmentation
- Sensors: RGB · 초분광(Vis-NIR/NIR) · Depth
- Tools: Git · Autodesk Inventor

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
