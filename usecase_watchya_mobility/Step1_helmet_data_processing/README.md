# Step1 : 데이터 취득, 전처리

## 폴더 구성

Step1 은 총 1개의 파일로 이루어져 있습니다.

## 환경

파일은 개인이 설치한 jupyter notebook 에서 실행됩니다.

python 3.6

opencv-python

## 차근차근 따라하기 위한 설명서

이 폴더의 .ipynb 파일을 정상적으로 구동하기 위해서는, 이전까지 과정의 결과물이 필요할 수 있습니다. 필요한 모든 중간 결과물을 함께 업로드되어 있으니, 환경을 잘 점검하셔서 중간부터 진행해도 괜찮습니다.

### 진행하기 위해 필요한 것들

해당 ipynb 파일을 진행하기 위해 필요한 파일들입니다. 파일들을 다운받아, 다음 환경에 적절히 배치할 수 있어야 합니다. 어려운 과정은 아니나, 처음 하는 작업이라면 꽤나 오랜 시간이 걸릴 수 있습니다. 초보자는 Step1 부터 차근차근 진행해 나가는 것을 추천합니다.

### 마치면 나오는 것들

하나의 ipynb 파일을 실행하면 나오는 결과물입니다. 마찬가지로 어떤 데이터일 수도 있고 어떤 모델 파일이 결과물일 수도 있습니다. 다음 단계의 ipynb 파일을 실행하기 위해 필요할 수 있습니다.

## 진행 과정

### 1-1-helmetdataprocessing.ipynb

- 1-1 을 진행하기 위해 필요한 것들
    - 헬멧 착용 데이터 파일1 : [다운로드 링크](https://drive.google.com/file/d/1QaMy1wigb7E0T4wPNElUERWwuRg0S186/view?usp=sharing)
    - 헬멧 미착용 데이터 파일1 : [다운로드 링크](https://drive.google.com/file/d/1p7svGkjQfg-p0cIjdMa59KyiYEv7jZVC/view)
- 1-1 을 마치면 나오는 결과물
    - 헬멧 착용 데이터 파일2 : [링크](https://drive.google.com/file/d/1PeyTi_bW23ZSYvybofnON-qOmi5aG0Bi/view?usp=sharing)
    - 헬멧 미착용 데이터 파일2 : [링크](https://drive.google.com/file/d/1p7svGkjQfg-p0cIjdMa59KyiYEv7jZVC/view)
- 여기서 무엇을 하나요?
    - 우리가 준비한 파일은, Kaggle 에서 다운로드받은 Helmet Detection Dataset 입니다.
    - Detection 을 수행하기 위해서는, 이미지 파일마다, 어디에 헬멧을 쓴 얼굴이 있는지 어디에 헬멧을 쓰지 않은 얼굴이 있는지를 나타내는 정보를 담은 파일이 필요합니다.
    - 이 파일의 정보를 바탕으로, 헬멧을 쓴 얼굴과 헬멧을 쓰지 않은 얼굴을 crop 해서 별도의 dataset 으로 만드는 작업을 하게 됩니다.
- 어려운 점이 무엇인가요?
    - 어느 부분이 잘려져서 저장될지 검사하는 것
    - 많은 파일들에 대해서 자동화된 스크립트를 일괄적으로 적용할 수 있도록 하는 것
    - 정확히 얼굴만을 crop 하면 학습 성능이 떨어질 수 있기 때문에, 적절한 margin 을 설정하는 것
    - margin 을 설정했을 때, margin 이 이미지 영역을 벗어날 경우에 대한 처리
