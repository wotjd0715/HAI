 ### Week 4 - 자율주행 Test
 ### **내용** 
 RC카를 운전하기 위해 모터 쉴드에 넣는 Input값과 주행영상을 저장하여 자율주행 모델을 학습시킬 Input 데이터셋을 만들었고
 모델 학습시킨 후 실제 트랙에서 테스트 진행하였다. 하지만 실시간 영상을 받아와 Line을 검출하고 모델에 돌리니 파이가 연산량을 따라 올 수 없어 실시간 이미지를 처리하여 RC카 제어하는 Input값
 전달에 Delay가 생겨 자율주행이 제대로 되지 않았다.   
 
 주행데이터 받기   
 ![image1](/document/images/image6.jpg)
 
 모델 학습률   
 ![image1](/document/images/image7.png)   
 ![image1](/document/images/image8.png)
 
 ### **어려웠던점**
 자율주행을 위해 라즈베리파이의 와이파이 모듈을 사용하여 노트북과 무선으로 연결했지만 자꾸 라즈베리 파이가 꺼지는 상황이 발생했다.
 우리는 그 이유를 단순히 발열로 인해 라즈베리파이가 죽은것이라고 단정짓고 파이를 에어컨에 식히면서 진행하였다. 하지만 몇시간을 발열을 
 식히며 파이가 꺼지지 않기를 빌며 자율주행 데이터를 모으는 고생(결국 모으지 못했다) 하고 난뒤 발견한 문제점은 라즈베리파이에서 자동으로 연결 와이파이를 바꾸려고 했기 때문이었다. 또 
 연결문제를 해결하여 학습 데이터셋을 모으고 학습을 시키는 와중에도 학습률이 그리 좋지 못했고 라즈베리파이 
 한개로 진행하다 보니 연산량을 따라오지 못해 Response Delay 문제가 발생했다. 이에 카메라 영상을 처리할 파이와 
 모델을 돌릴 파이 2개로 나누어도 보았지만 역시 자율주행이 제대로 되지 않았다.
 
 ### **배운점**  
돌이켜 보았을때 자율주행이라는 주제의 난의도와 방학이 끝나기전 마무리를 지으려는 마음에 프로젝트를 진행함에 있어
충분한 지식이 없는 상태에서 진행하게 되었다. 그래서 문제가 발생했을때 차분히 원인을 따져보지 못하고 눈에보이는 한가지(발열)로 단정지어 
이것만 해결하면 되겠지하며 진행한 부분이 많았다. 그렇게 진행하다보니 몸을 고생해나가면서 차차 문제가 발생했을때 하나하나 차분히 원인을 따져보며
진행을 하게되었고 또 내가 알지못했던 부분에서 문제가 발생할 수 있다는것을 배우게 되었다.

 **박재성**   
프로젝트를 진행하면서 가장 아쉬운 주차가 아닌가 싶다. 프로젝트의 완성을 직전에 앞둔상태에서(완성도는 떨어지지만) 라즈베리파이가 자꾸 
죽는 바람에 프로젝트 진행이 지체되고 있다는 생각에 조바심이 났던겄 같다. 문제가 발생했을때 다른 원인들을 생각해낼 수 있었다면 좀더 완성도를 
높일 수 있지 않았나... 그래도 이러한 프로젝트들로 쌓인 경험들을 통해 다음에는 더 잘해나가는 것이 아니가 싶다.   
특히 이전에 혼자 인공지능을 공부했을때는 학습데이터셋을 sklearn과 같은 곳에서 다운받아 사용했지만 이번 프로젝트에서는 직접 수집하고 가공한 데이터로
인공지능을 학습시켜보고 어느정도 성과(정확도가 75%정도였지만)를 내본것이 가장 좋았다. 반면 가장 아쉬웠던 점은 라즈베리파이가 연산속도를 따라오지 못하자
카메라의 Frame수를 줄여 초당 연산이미지량을 줄이면 Delay가 적어질것이라고 판단해 시도해 보았다.
사실 성공해야 했지만 당시 밤을 새가며 20시간 연속으로 같은 프로젝트만 하고있어서 코드를 잘못고쳐서 그냥 안되는줄 알고
다른 방법을 찾았던 것이다. 나중에 Feedback을 하며 이 사실을 알고 수정후 성공했을때는 정말 너무 아쉬웠다. 

 
 **양영우**   
 라즈베리파이가 계속적으로 다운이 되는 현상이 있었고 처음에는 라즈베리파이의 발열로 인한 다운으로 생각을 하고 충분히
 발열이 줄어든 뒤 다시 실행을 하였고 같은 상황이 계속 반복이 되었다. 발열 문제라고 생각을 하여 다른 시도를 하지 않고 있었다가 문제점을 두 가지 발견하였다.   
 우선 와이파이를 연결할 때 다른 두 개의 와이파이를 바꿔가며 연결이 되어 접속이 끊기는 현상이 있었고
 연상량이 오버되어 다운이 되는 현상이 있었다. 이 문제를 해결하기 위해 와이파이 연결을 해제하고 라즈베리파이를 하나 더 연결하여 연산을 분산시키니 해결이 되었다.   
 이로써 문제가 발생을 하였을 때 하나만 생각을 할 것이 아니라 다른 것도 함께 생각을 하며 문제를 해결을 해야 되는 것을 깨닫게 되었다.   
 직접 RC카를 운전을 하여 영상 데이터와 운전 값을 받아 학습을 시킬 수 있었고 padding, kernel size, filter, stride등을
 바꿔가며 학습을 시켰고 가장 뛰어난 학습을 찾을 수 있었다. 학습을 가장 잘하는 것을 찾기 위해 데이터 전처리 과정을 바꿈으로써 더 잘 학습을 시킬 수 있는 것을 배웠다.

 **권현수**  
 4주차가 가장 힘들었던 이유는, 어떤 문제가 생겼지만 그 이유를 엉뚱한 곳에서 찾았기 때문이라고 생각한다. 라즈베리파이를 원격 연결해야하는데, 모바일 핫스팟을 통해서 연결을 했고,  
 그것이 잘 안되었는데, 우리는 이유를 라즈베리파이의 발열문제로 삼았었다. 실제로 열을 식히니 잘 연결되는 우연이 몇번 발생했기 때문이다. 하지만 진짜 문제는 핫스팟이 여러개가 켜져있었고,  
 라즈베리파이가 연결을 여기저기 바꿔갔기 때문에 연결이 잘 안된 것이었다. 이 큰 문제를 뒤로, 학습하는 과정에 들어섰다. 학습과정은 영상을 따로 빼와서 찍고, 저장한 다음, 그동안 운전자가  
 입력한 내용을 txt파일로 저장하여 이 두개의 싱크를 맞춘 다음에 인공지능 학습을 시키는 것이었다. 이 과정에서 학습이 제대로 되기위해 영상의 전처리 과정을 새롭게 조정하였고, 가중치의 값 등등  
 여러가지를 바꿔 점점 완성도 있는 자율주행 자동차가 되어가고 있는 것을 느꼈다.

 **윤동준**   
 1개의 라즈베리파이에는 카메라 모듈, 다른 1개의 라즈베리파이에는 모터드라이브를 연결한 후 PWM 값을 설정한 후 직접 키보드를 통해 제어를 하였다. 라인을 따라 주행
하는 영상을 카메라 모듈을 통해 녹화하였고, 키보드 인풋값과 비디오를 통해 필터 개수, 패딩, 활성화 함수 등을 바꿔가면서 학습을 시켰다.
<br/>어려웠던 점은 Hardware적으로는 원래 라즈베리파이를 유선으로 컴퓨터에 연결하여 VNC를 통해 Control하다가, Wifi로 통신하는 방법을 찾아서 Wifi로 통신하였는데, Raspberry Pi의 와이파이 연결이 계속 바껴서 통신이 자꾸 끊어졌었다. 그것도 모르고 발열이 너무 심해서 통신이 끊긴다고 생각했던 나머지 계속 에어컨 밑에서 식히고 구동해보고 하는데 시간을 많이 잡아먹은 것 같다. 
SoftWare적으로는 차선을 인식하는 것 이후부터는 Convolution과 Pooling에 대한 지식이 부족해서 어떤 값을 조정해야 학습률이 높게 나오고 과적합이 되지 않는지 몰랐다. 그래서 마구잡이로
값을 변경시켜 봤다. 다음 자율주행 자동차 프로젝트를 진행하게 된다면 기초지식을 더 탄탄히 공부하고 실험해봐야 할 것 같다. 

 **이상목**

 **이진우**
