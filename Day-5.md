# IAM 역할

<br>

![스크린샷 2023-03-18 오후 3 48 07](https://user-images.githubusercontent.com/81137234/226090139-91fc3aaf-70f2-4bc5-a9c6-9e9fb5d0bb8c.png)

<br>

ec2를 클릭하고 넘어간다.


<br>

![스크린샷 2023-03-18 오후 3 50 59](https://user-images.githubusercontent.com/81137234/226090228-81182322-cef4-4609-be1c-fc4b260ae113.png)

<br>

ec2 인스턴스가 뭘 할 수 있는지 보여준다.  


<br>

![스크린샷 2023-03-18 오후 3 52 13](https://user-images.githubusercontent.com/81137234/226090275-93a96bf6-7666-4805-bd55-985afa90d101.png)

<br>

이름을 지정하고 넘어간다.

<br>

![스크린샷 2023-03-18 오후 3 52 59](https://user-images.githubusercontent.com/81137234/226090299-969bb84f-ed20-45d5-9898-e0cf1d8c15d5.png)

<br>

롤 섹션에 역할이 생성되었다.

<br>

IAM 역할을 만들 때 누가 이 역할을 맡을 수 있는지 담당자(Principal)를 지정해야 하는 신뢰 정책(Trust Policy)이 추가되어야 해당하는 IAM 사용자 지정할 때 편하다.  

즉, 담당자가 이직을 했다? -> 이 역할을 다른 iam 유저한테 지정만 해주면 되는 것.(대략 이렇게 이해했다.)

<br>