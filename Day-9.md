# EC2 - EBS 볼륨 snapshot

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 47 30" src="https://user-images.githubusercontent.com/81137234/227106213-0aa7d0ea-a6c6-48aa-8f2f-ea9f72344b93.png">

<br>

볼륨을 생성하고 스냅샷을 생성한다. 

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 50 31" src="https://user-images.githubusercontent.com/81137234/227106421-7cbb9715-c506-446d-8fad-8c780bc5a481.png">

<br>

위와 같이 연결되어있는 볼륨의 스냅샷을 알 수 있다.

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 51 48" src="https://user-images.githubusercontent.com/81137234/227106558-55e860bb-ccc7-40dd-b718-7ba9ecfc948d.png">

<br>

스냅샷 복사를 하면 원하는 리전으로 스냅샷 사본을 생성할 수 있다.

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 52 49" src="https://user-images.githubusercontent.com/81137234/227106755-0910bf6b-4e9e-407e-8e6e-bd6347f7e917.png">

<br>

스냅샷을 가지고 볼륨을 만들 수도 있다.

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 54 23" src="https://user-images.githubusercontent.com/81137234/227106937-236f3b4d-bd1e-4efc-95cd-597bb36898f7.png">

<br>

실수로 스냅샷이나 볼륨을 삭제하는 것을 방지하기 위해 recycle bin(휴지통) 서비스를 이용할 수 있다.

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 55 37" src="https://user-images.githubusercontent.com/81137234/227107197-b7259125-3896-41ea-be6e-b0da3b267e69.png">

<br>

다음과 같이 보존 규칙을 생성할 수 있다.

<br>

<img width="500" alt="스크린샷 2023-03-23 오후 1 57 57" src="https://user-images.githubusercontent.com/81137234/227107500-f50ecc28-976e-4d46-8a9c-4fb823a7b8cf.png">
<img width="500" alt="스크린샷 2023-03-23 오후 1 57 21" src="https://user-images.githubusercontent.com/81137234/227107520-eeed7841-7b36-4790-9540-7787b468d9e5.png">

<br>

스냅샷을 삭제했다면, recycle bin(휴지통)에 스냅샷이 뜬다.  
이것을 recover 하면 다시 스냅샷이 해당 리전에 생성된다.

<br>