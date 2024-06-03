### AUC: area under the curve (곡선 아래 면적)

---

AUC는 머신러닝의 분류 모델 성능을 평가하는 핵심 지표 중 하나이다. 일반적으로 AUC는 [ROC곡선](../r/ROC.md) 또는 PR곡선 아래의 영역을 나타내며, 특히 [이진 분류](../b/Binary_Classification.md) 문제에서 유용하게 사용된다.

<img src="https://developers.google.com/static/machine-learning/crash-course/images/AUC.svg?hl=ko" title="" alt="https://developers.google.com/static/machine-learning/crash-course/images/AUC.svg?hl=ko" width="263">

AUC는 가능한 모든 분류 임곗값에서 집계된 성능 측정값 제공

AUC의 값의 범위는 0~1 이다.

예측이 100% 틀린 모델의 AUC는 0.0이고, 예측이 100% 정확할 경우 AUC는 1.0이다.


