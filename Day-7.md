# EC2 보안그룹

<br>

![스크린샷 2023-03-21 오후 7 13 07](https://user-images.githubusercontent.com/81137234/226576030-608ffeed-baae-47e6-9ca2-34d46d44a9f6.png)

<img width="588" alt="스크린샷 2023-03-21 오후 7 25 34" src="https://user-images.githubusercontent.com/81137234/226579138-acd0a519-0c89-4014-b6ff-5dc7141da73d.png">

<br>

위 처럼 ec2를 만들때 사용자 AMI에 사용자 데이터를 넣어서 만들 수 있다.  
참고로 맨 위 #!/bin/bash 부분 빠트리면 index.html이 제대로 안떠서 방화벽 확인해보라는 페이지가 뜰 것이다.  
그러니까 2번째 사진처럼 다 넣어야한다.

<br>

![스크린샷 2023-03-21 오후 7 04 37](https://user-images.githubusercontent.com/81137234/226574212-88012a73-e158-4dc1-81c2-f77b4748f2ca.png)

![스크린샷 2023-03-21 오후 7 05 23](https://user-images.githubusercontent.com/81137234/226574381-cd221a03-5198-4871-8431-1101f3b9945a.png)

<br>

ec2를 생성해보면 보안 그룹이 2개가 있다는 것을 알 수 있다.  
1개는 기본적으로 생성되어 있는 default 보안그룹이고  
1개는 ec2가 만들어짐에 따라서 생성한 보안그룹이다.  

<br>

![스크린샷 2023-03-21 오후 7 07 43](https://user-images.githubusercontent.com/81137234/226574857-a00bdb96-4486-4bf0-9132-83369d792175.png)

<br>

기본 보안그룹 말고 생성된 보안그룹에 80번 포트를 인바운드 규칙에 넣었다.  
또는 ec2 생성할 때 http 체크박스 누르면 80번 포트가 넣어져서 보안 그룹이 만들어진다.

<br>

![스크린샷 2023-03-21 오후 7 22 02](https://user-images.githubusercontent.com/81137234/226578129-0e6863ad-3e18-49e9-a612-cbb2f0e257b5.png)

<br>

그래서 퍼블릭 ip를 이용해 접속을 해보면 된다.

<br>
