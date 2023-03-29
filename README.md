# 🔮 감정 음성 데이터 분석: 과적합 방지 고찰

## 실시간 감정분석 화상회의 및 감정상황 회의록 서비스
🥉 민교수님의 논문 투고 장려

## 프로젝트 관련 링크
발표용 슬라이드: https://docs.google.com/presentation/d/1ysadmKWzAK9TvJ8QxTdkTegd7T5-nAVor1_x6cmYPDI/edit#slide=id.p

## ✨ 프로젝트 소개
![image](https://user-images.githubusercontent.com/58973535/228566697-8079796c-57a3-4547-b3aa-d66729a0d163.png)

음성데이터에서 특징을 추출하여 기쁨, 당황, 분노, 불안, 슬픔 총 5개의 감정을 분류하는 모델을 설계

1. mfcc와 mel spectrogram을 이용하여 음성데이터에서 특징을 추출

![image](https://user-images.githubusercontent.com/58973535/228572324-1f78a065-da26-4f97-9e1b-345e2612c264.png)

2. LSTM 모델 사용

![image](https://user-images.githubusercontent.com/58973535/228572453-a7aa186c-74e3-4a0d-9022-a06fd4a2a0ab.png)

-> 과적합 발생 !

3. 음성데이터를 8등분 후 랜덤으로 병합

![image](https://user-images.githubusercontent.com/58973535/228574042-33863828-1cee-44ab-a9fa-025c3c47ba48.png)

https://user-images.githubusercontent.com/58973535/228573752-ca3aaa49-0efd-4321-a439-94151d6f7fba.mp4

4. 랜덤으로 이어붙인 음성데이터에서 mfcc와 mel spectrogram을 이용하여 특징 추출

5. LSTM, ResNet, Efficient Net, Random Forest 모델을 사용

|모델명|train accuracy|test accuracy|top-2 accuracy|
|---|---|---|---|
|LSTM|0.6087|0.4073|0.7120|
|ResNet|0.6213|0.4653|0.6967|
|EfficientNet|0.5170|0.4487|0.6947|
|RandomForset|--|0.4107|--|
