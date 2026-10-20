### [Healthcare AI] MIMIC-IV 대규모 임상 데이터 기반 응급실 입원 예측 파이프라인 구축
> ** 프로젝트 | 💡 Role: Data Engineer**
- **Problem:** 응급실 혼잡 상황에서 환자의 초기 중증도가 낮아 보이더라도 실제 입원으로 이어질 가능성을 조기에 식별하여, 선제적으로 환자 우선순위를 결정하고 병상 및 의료 인력 배치를 최적화해야 함.
- **Action (Data Engineering & Feature Extraction):**
  - 42만 건 이상의 MIMIC-IV 데이터 전처리 과정에서 발생하는 활력징후 결측치(약 38만 건) 문제를 MICE 알고리즘을 활용해 다중 대체(Multiple Imputation)하여 데이터 무결성을 확보함.
  - 단순 생체 측정값을 넘어, 심박수와 수축기/이완기 혈압을 조합한 Shock Index(쇼크지수) 및 MAP(평균동맥압) 등 임상적 도메인 지식이 반영된 파생 변수를 설계하여 예측 성능을 고도화함.
- **Action (Modeling & Clinical Validation):**
  - 로지스틱 회귀 및 랜덤 포레스트 모델(AUC 0.777)을 구축하여 초기 활력징후와 ICD 카테고리만으로 유의미한 분류 성능을 달성함.
  - 통계적 분류 지표(Accuracy, F1-Score)에만 의존하지 않고, 실제 임상 현장에서 모델을 적용했을 때 얻는 실질적인 순이득(Net Benefit)을 평가하기 위해 DCA(Decision Curve Analysis, 의사결정곡선분석)를 도입하여 비즈니스/임상적 타당성을 검증함.
- **Stack:** R, Random Forest, Logistic Regression, MICE
