---
title: "[번역] ICLR 2020: NLP Highlights"
date: 2020-06-03 +0800
categories: 블로그 번역
---
원본은 post는 [original-ICLR2020-post] 여기를 보시면 됩니다.

![image2](/images/icrl_logo.png)

1. About ICLR 2020
"The International Conference on Learning Representations”
NIPS, ICML과 함께 top-tier AI conference 이졍.

2. Techonology Trend
참고: 글쓴이가 NLP 쪽이라 그쪽에 포커싱 많이 되어있음
* Hot Topics:
    * Transformers and pre-trained lauguage models are still very hot topics
        * “Attention is all you need, 2017" 과 “BERT, 2018” 이 SOTA 찍고 난 후에 연구자들은 계속 transformer’s 구조와 pre-trained lm에 대해 활발히 연구중
        * 이론증명 측면에서도 논문이 나오고
        * Transformers와 pre-trained lm의 성능을 올리는 것도 논문의 한 결
        * 모델 사이즈 줄이기 또는 훈련시간 줄이기도 눈문의 한 결
        * 기존 LSTM, RNN도 역시 깊이있게 탐구되고 있음
* 새로 떠오르는 토픽들
    * multilingual /. ross-lingual tasks를 위한 language architectures and models
    * 비전이나 NLP쪽 모두를 위한 양자-inspired 알고리즘
    * multimodal model
    * Reinforcement learning and NLP 다른 학문 분야와 제휴하는.
    * Model Compression / Pruning

3. 글쓴이의 생각
* Yann LeCun과 Yoshua Bengio의 딥러닝의 방향에 대한 담화는 통찰력있는 대화였어요. 예를들어, NLP에서 성공했던 self-supervised learning을 Vision 문제에 어떻게 적용할지, 양자 알고리즘에 대해서 그들이 어떻게 생각하는지, 신경과학의 아이디어도 중요하다 는 둥의. 그들이 현재 진행하고 있는 것들을 듣는것도 도움이 되었답니다.

4. Details: Highlights of. elected papers:
* Cross-lingual abiliry of multilingual BERT: An Empirical study (경험적인 연구결과), from upenn
    * multilingual model에 대해 흔한 가설중에 하나는 '언어간의 lexical overlaps가 많이 있는애들이 학습이 잘 된다’ 라는건데, 이 논문에서 말하길 “언어간의 lexical overlap은 cross-lingual success에서 없는거나 다름없는 역할을 한다. 다만 네트워크의 depth는 핵심적인 역할을 한다” 하고 한다.
        * YJ. 이게 BERT가 그런거라면 일반 e2e 음성인식 모델도 다른 언어 우두두두 넣고 깊게 학습하면 더 잘 될지도!?!! 해보자.
* ELECTRA: pre-training text encoders as discriminators rather than generators
    * (YJ. 자세히는 모르겠지만 엄청나긴한데.. low-computing resource로 훈련하는 방법이)
    * 각자 lm pre-train 할 때 만들 때 low-computing resources 사용하는 것의 새 장을 연 논문
    * 저자는 gpu로 4일 학습해서 GPT(30x 더 compute 해야하는) 성능 능가했음, GLUE natual language understanding benchmark task에서.
* On the relationship between self-attention and convolutional layers
    * NLP에서 RNN을 attention-based model로 성공적으로 바꾸고 난 뒤에, 연구자들은 지금 vision에서 convolutional layer에 똑같은 짓을 할 수 있을지에 대해 연구하고 있음
    * 저자들이 말하길, 충분한 갯수의 head를 가진 multi-head self-attention layer는 적어도 any convolutional layer만큼은 표현 잘 한다.
    * 실험적으로 self-attention layers가 CNN layers랑 비슷하게 pixel-grid 패턴에 attend함으로써, 저자들의 분석을 입증했다.
* Are Transformers universal approximators of sequence-to-sequence functions?
    * (이건 좀 이론적인 논문) 저자들은 “transformer model이 compact domain에서 임의의 연속된 sequence-to-sequence functions를 보편적으로 근사할 수 있다는걸 보여주겠어요.” 라고 했다. 저자들은 고정된 width의 self-attention layers가, transformer의 보편적 근사 특성에 key 역할을 하며, input sequences의 contextual mappings를 계산할 수 있다는 것도 입증했다. 


[original-ICLR2020-post]: https://towardsdatascience.com/iclr-2020-nlp-highlights-511deb99b967
