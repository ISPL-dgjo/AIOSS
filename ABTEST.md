# 🧪 A/B Testing Report: CNN 기반 VVC 고속 블록 분할 구조 결정 알고리즘

## 📌 1. Hypothesis Statement

> **We believe** that  
> VVC 인코딩 중 복잡도 감소를 필요로 하는 연구자 및 개발자  
> **want** 기존 CU/QP 외에도 Edge map과 주변 CU 정보를 활용하는 알고리즘  
> **because** 이로 인해 인코딩 복잡도를 더 줄이면서도 BDBR 성능을 유지 또는 향상시킬 수 있기 때문이다.

### 🎯 Hypothesis (If–Then Format)

If we include additional input features such as edge maps and neighboring CU information
into our CNN-based block partitioning decision algorithm,
Then we expect to reduce encoding complexity by more than 25%
while keeping BDBR loss below 1% compared to the baseline VTM model.


---

## 🧪 2. Experiment Design

| 항목                    | 내용                                                                                   |
|-------------------------|------------------------------------------------------------------------------------------|
| **What’s the change?**  | Edge map과 주변 CU 정보를 CNN 모델에 추가 입력으로 활용                                |
| **Expected impact**     | 복잡도 25% 이상 감소, BDBR 1% 이하 손실 또는 성능 향상                                  |
| **Customer segment**    | 인코딩 복잡도 감소를 원하는 연구자, 인코더 개발자, 실시간 인코딩이 필요한 시스템 개발자 |
| **How much change?**    | 복잡도 25% 감소, BDBR 성능 손실 1% 이하                                                 |
| **Duration**            | 2주 (Week 1: 기존 모델, Week 2: 개선 모델)                                               |
| **Baseline**            | VVC Test Model (VTM 10.0) 결과와 비교                                                    |

---

## 🔗 3. OKR와 A/B Testing 연관

### 🎯 Objective  
CNN 기반 VVC 고속 블록 분할 구조 결정 알고리즘 개발

### 📈 Key Results

- ✅ U-Net 및 Multi-task MLP를 활용한 알고리즘 개발 완료  
- ✅ VTM 대비 인코딩 복잡도 25% 이상 감소  
- ✅ VTM 대비 BDBR 손실 1% 이하  
- ✅ 최신 연구 대비 성능 및 효율 향상  
- ✅ SCIE급 논문 초안 작성 및 제출 완료 예정  

### 🔁 OKR와 A/B Testing의 연관성

본 A/B 테스트는 위 Key Results 달성 여부를 검증하는 **실험적 수단**이며, 특히:
- "Edge map + 주변 CU 정보" 전략이 실제로 성능 향상에 기여하는지를 입증
- 실험을 통해 OKR 성과를 **정량적 데이터**로 확인하고 피드백 루프를 완성함

---

## 📊 4. 실험 세부 설계

### 실험군 구성

| 그룹         | 입력 구성                                 | 모델 구조     | 비교 기준     |
|--------------|--------------------------------------------|----------------|----------------|
| Control      | CU, QP                                     | 기존 CNN 모델 | VTM 성능 기준 |
| Experiment   | CU, QP + Edge map + 주변 CU 정보           | 개선된 CNN 구조| 동일 기준     |

### 측정 지표

- ⏱ **Encoding Complexity**: 평균 인코딩 시간, 연산량(FLOPs)
- 📉 **BDBR**: Bitrate-Quality Tradeoff (VTM 대비 성능 손실율)

---

## ✅ 5. Expected Outcome

- 실험 결과가 예상대로라면, 개선 모델은 기존 대비 **복잡도 25% 이상 감소** 및 **BDBR 성능 1% 이내 저하**를 보일 것으로 기대
- 해당 결과를 기반으로 SCIE급 논문 결과물에 포함 가능

---

## 📌 참고 사항

- 실험은 동일한 비디오 시퀀스, 동일 QP 값, 동일 환경에서 수행
- 사용 도구: VTM 10.0, Python 기반 모델 구현, BDBR 계산 스크립트
- 실험 환경: Ubuntu 22.04, NVIDIA A100 GPU, CUDA 11.8

---

