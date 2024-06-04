### Attention

---

**"문장내에서 서로 관련 있는 정보를 모두 유지할 수 없을까?"** 라는 의문에서 시작

**"context vector 뿐만 아니라, 서로 관련있는 정보도 각 input words가 갖도록 해보자"** 라는 해결책 제시

즉, **모델이 문장을 만들 때, encoder에서 가장 관련이 높은 정보를 확인할 수 있도록 하자**

기존 encoder decoder 모델에서는, encoder LSTM의 마지막 state만 context vector로 사용했다.

하지만 context vector를 만들때 모든 단어의 embedding을 강조하며 hidden states의 weighted sum을 얻는 방법을 제안했다.

어텐션의 기본 아이디어는 디코더에서 출력 단어를 예측하는 매 시점(time step)마다, 인코더에서의 전체 입력 문장을 다시 한 번 참고한다는 것이다. 단, 전체 입력 문장을 전부 다 동일한 비율로 참고하는 것이 아니라, 해당 시점에서 예측해야할 단어와 연관이 있는 입력 단어 부분을 좀 더 집중(attention)해서 보게 된다.

### Attention Function

---

<img src="https://wikidocs.net/images/page/22893/%EC%BF%BC%EB%A6%AC.PNG" title="" alt="alt text" width="328">

어텐션을 함수로 표현하면 주로 다음과 같이 표현된다.  
**Attention(Q, K, V) = Attention Value**

어텐션 함수는 주어진 '쿼리(Query)'에 대해서 모든 '키(Key)'와의 유사도를 각각 구한다. 

그리고 구해낸 이 유사도를 키와 맵핑되어있는 각각의 '값(Value)'에 반영해준다. 

그리고 유사도가 반영된 '값(Value)'을 모두 더해서 리턴한다. 

> Q = Query : t 시점의 디코더 셀에서의 은닉 상태
> K = Keys : 모든 시점의 인코더 셀의 은닉 상태들
> V = Values : 모든 시점의 인코더 셀의 은닉 상태들
