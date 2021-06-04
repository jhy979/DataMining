# DataMining
데이터마이닝 수업입니다.
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
파이토치를 사용하여
