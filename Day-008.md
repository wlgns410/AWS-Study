# EC2 - EBS 볼륨 설정

<br>

![스크린샷 2023-03-22 오후 4 27 29](https://user-images.githubusercontent.com/81137234/226830770-511d5e4e-ea2b-4973-8d35-05ed6bfd2ab1.png)

<br>

ec2를 생성하면 스토리지 탭에 ebs 볼륨이 있다.

<br>

![스크린샷 2023-03-22 오후 4 29 43](https://user-images.githubusercontent.com/81137234/226831146-d305323a-279a-4269-a9b8-b2bf2c6ba99e.png)

<br>

지금은 볼륨이 1개뿐이지만, 고유한 볼륨을 생성할 수 있다.

<br>

![스크린샷 2023-03-22 오후 4 30 49](https://user-images.githubusercontent.com/81137234/226831341-71c5f005-bc8e-4d7c-b318-72e274d68080.png)

<br>

볼륨을 생성해주자.  
참고로 루트 볼륨과 같은 가용영역을 선택해야한다.  
나는 ap-northeast-2c인데, 2a를 2c로 바꿔주어야한다.  

<br>

![스크린샷 2023-03-22 오후 4 31 28](https://user-images.githubusercontent.com/81137234/226831514-f8f3594d-dfa6-419e-9626-2bd9e2fed27d.png)


<br>

![스크린샷 2023-03-22 오후 4 34 23](https://user-images.githubusercontent.com/81137234/226831994-b08db9d3-2bc9-4311-a9b7-b1f2fc422eea.png)

<br>

가용영역이 같으면 ec2 인스턴스가 뜨고, 다르면 안뜬다.

<br>

![스크린샷 2023-03-22 오후 4 35 18](https://user-images.githubusercontent.com/81137234/226832185-b776724d-9a9c-4d42-a80a-87f89e888f85.png)

<br>

ec2 인스턴스를 확인해보면 2개의 ebs 가 연결되어있는 것을 확인할 수 있다.  

<br>

![스크린샷 2023-03-22 오후 4 39 28](https://user-images.githubusercontent.com/81137234/226833000-7e95644c-473f-4a78-842c-32bd3944bb3f.png)

<br>

테스트가 끝났으니 ec2 인스턴스를 삭제했다.  
그랬더니 루트 볼륨은 자동삭제 체크가 되어있어서 삭제가 되었다.  
하지만 추가한 볼륨은 자동삭제 항목이 없었으니 남아있는다.  
추가적으로 생성한 볼륨도 삭제해준다.

<br>


