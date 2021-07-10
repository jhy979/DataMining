# DataMining
### 데이터 마이닝
- 정말 어려웠던 수업입니다. 괜히 대학원생 강의를 듣겠다는 객기를 부리는 게 아니였는데 ㅠㅠ <br> C 나 C++은 너무나도 익숙하지만 Python은 Convolution layer를 구현하는 과정에서 사용하기 위해 정말 기본만 익혔던 기억이 있었습니다. (아마 작년 system programming 수업 4번째 프로젝트 때?) 이 수업은 머신러닝 수업이기 때문에 numpy나 pytorch, keras를 사용해야만 했기에 저에게는 짧은 시간에 낯선 언어로 어려운 머신러닝 알고리즘들을 모두 구현해내야하는 굉장히 디멘딩한 수업이였습니다.. 하지만 그만큼 얻어가는 것도 많다는 생각이 드네요. 
- 제가 배웠던 내용들에 대하여 간단한 목차를 표로 정리해보겠습니다.

|알고리즘|내용|
|:--:|:--:|
|ANN|artificial ..|
___
## 과제1  
<br/> 기본적 파이썬 문법을 익히고 numpy를 이용해보는 과제였습니다. 머신러닝을 시작하기 전 기본적 소양을 배울 수 있었습니다.
___
## 과제2 
<br/> **KNN**을 구현하는 과제였습니다. 라이브러리도 이용할 수 있지만, 그보다 실질적으로 알고리즘을 이해하고 직접 짜보는 것에 집중해보는 시간이였습니다.  MNIST 데이터 셋에 대하여 KNN 알고리즘으로 test 데이터의 label 값을 예측하여 return 해주는 함수를 만들고, 실제 label 값과 비교하여 예측 정확도를 구해보았습니다. 
<br/> <br/> 또한 training dataset을 여러 번 split하여 K fold cross validation을 수행하고 최적의 hyper parameter K가 어떤 값을 가질까? 에 대하여 알아보았습니다. (확실히 Scikit-learn 라이브러리를 사용하면 정말 편안하구나... 느꼈습니다만 그래도 직접 해보니 KNN 알고리즘을 C로 작성해보고 싶은 생각이 들어 C로도 작성해보는 시간도 가질 수 있었습니다.)
<br/> <br/> 마지막으로는 Numpy Library만 사용하여 MLP(one hidden layer)를 사용하는 Softmax Classifier를 만들었습니다. 개념적으로는 이해가 금방 갔던 내용들이나, 직접 구현하는 부분에 있어서는 불편한 점들이 있었습니다. 이 과정에서 요새 많이 쓴다는 one-hot encoding을 알게 되었습니다.
___
## 과제3  
<br/>
이제 라이브러리를 이용하여 sklearn에서 제공하는 3가지 데이터에 대하여 여러 가지 분류 알고리즘을 진행해봤습니다. 라이브러리를 사용하니깐 정말 너무 편함을 느꼈습니다. 다만, 여기에 젖어 각 알고리즘이 어떻게 동작하는지에 대해 잊어버리는 것에 대하여 경각심을 가져야할 것 같습니다.
<br/><br/>
사용 알고리즘
<br/>
1. CART <br/>
2. Random Forest<br/>
3. XGBoost<br/>
4. LightBGM<br/>
5. Naive Bayes<br/>
6. SVM<br/>
7. MLP<br/>
8. Ensemble
<br/><br/>
<img src = https://user-images.githubusercontent.com/32920566/117388152-26878b00-af25-11eb-9d41-d356bd126212.JPG />
다음과 같은 효율이 나왔습니다. 여기서 사용한 sklearn built-in data들은 사이즈가 작아서 금방 돌아갔지만, kaggle에서 데이터가 방대한 친구를 데려온 결과 SVM은 엄청난 시간이 걸렸습니다.( SVM은 마진까지 최대화해야하기 때문인가..)

___
## 과제4
<br>
대표적인 이미지 데이터인 cifar10을 불러와서 분류하는 작업을 해봤습니다. MLP와 CNN을 구현해봤는데요, 아래 그림에서 정확도를 보실 수 있습니다.
MLP에서 skip connection 방식으로 코드를 작성하였고, CNN은 ResNet 방식을 이용하였습니다. 처음엔 무슨 소리인지도 몰랐는데 몇 주 잡고 있다보니깐 이해가 되더라구요. 특히 ResNet 구조를 잘 설명한 블로그 글을 보니깐 어느정도 해결했습니다. 사실 제 코드는 제가 처음 짜보는거라 매우 불완전합니다. ModuleList로 block의 개수에 따라서 깔끔하게 짰어야했는데 그냥 Sequential로 작성한 부부도 있고... 그래서 조금 더 시간이 날 때 수정해보고, epoch를 늘리는 방식이 아니라 구조를 바꿔서 accuracy도 증가시켜봐야겠습니다. 근데 와.. 맨땅에 헤딩이였는데 역시 해보니깐 되긴하네요!

<img src="https://user-images.githubusercontent.com/32920566/120741701-77909c00-c530-11eb-8f2d-70c1afa609a0.png" width="400px" height="600px"/><br>
위의 표는 train data에서 뽑은 validation set으로 측정한거라 정확도가 높게 나온겁니다. 조금 overfitting 되어서 그런 감이 있나 싶긴했는데 다른 분들도 대부분 이런 형태로 그래프가 작성되더라구요. train에서 학습하고 train에서 뽑은거니 그럴 수 밖에 없지 않을까 싶긴합니다. 후 과제 어려웠다~

___
## 과제5
<br>
2020년 10월에 나온 따끈따끈한 Vision Transformer를 사용해봤습니다. 이미지 인식에서 요새 화제라고 하는데요, 역시나 역시나 어렵긴 했습니다.<br><br>

![image](https://user-images.githubusercontent.com/32920566/120909713-cf571080-c6b2-11eb-996b-1be632c016f0.png) 
<br><br>

이해를 위해 이미지를 추가했습니다. 이미지를 여러 개의 패치로 쪼개고 마치 단어 다루는 것처럼 벡터화를 하는데 이를 flatten하여 사용합니다.<br>
순서대로 설명을 해보겠습니다.
1. self attention
- 문장 사이 각 단어끼리 연관성을 파악하는 일입니다. 이미지에 있어서는 벡터끼리 dot product를 하고 softmax를 통해 연관성을 파악합니다.
2. Multihead attention
- self attention을 병력적으로 나누어 계산하는 과정입니다. Query, Value, Key 값의 차원을 맞춰주고 수정하는 일을 합니다.
3. Positional Encoding
- 순차적으로 입력된 값들을 상대적인 위치정보를 나타냅니다. Sin/Cos을 사용하여 -1 ~ 1 사이의 값을 가지게 됩니다.

<br>

👇👇 실제 구현 accuracy입니다. 62%가 나왔네요. 더 높이려고 parameter 튜닝도 해보고 했으나.. 일단 여기까지가 최고 accuracy네요 ㅠㅠ<br><br>
<img src="https://user-images.githubusercontent.com/32920566/120909680-6e2f3d00-c6b2-11eb-9a7a-6d3ec8fa7445.png"/> <br>

