# AWS IAM MFA

<br>

아래와 같은 순서를 따른다.

1. IAM User 생성  
2. IAM Role 부여  
3. MFA 설정  
4. google OTP로 6자리 비밀번호 받기  
5. 생성된 역할전환링크로 접속해서 역할 전환  
6. IAM 계정 로그인 확인  


- 우선 IAM User를 생성한다.
    
AWS IAM - 액세스 관리 - 사용자 탭 에서 사용자 추가를 누른다.  
아래와 같은 ID와 PASSWORD 설정 화면이 나오는데, 사용자이름이 id가 되고 콘솔 비밀번호가 PW 가 된다.  

<br>

![스크린샷 2023-03-17 오후 4 26 33](https://user-images.githubusercontent.com/81137234/225839981-5394aee2-ae54-4939-a6d3-d04fb0b6eb01.png)

<br>

참고로 비밀번호 재설정 필요 체크박스 선택시 IAMUSERChangePassword 권한을 추가해야하니까 편의를 위해서 해제해주는 편이 좋다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 44 40" src="https://user-images.githubusercontent.com/81137234/225836011-f8deba89-dbca-4386-9295-3bfdc2651f52.png">

<br>

여기서 권한 설정을 하지 않고 넘어간다. 왜냐하면 뒤에서 추가해줄 것이기 때문이다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 45 34" src="https://user-images.githubusercontent.com/81137234/225836110-a46566bd-acbb-43c1-9f7c-14bcbffc5d8f.png">

<br>

태그 추가도 넘어가준다. 선택사항이기 때문

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 46 24" src="https://user-images.githubusercontent.com/81137234/225836200-b9064650-26fd-4f75-b5b7-0239a9b70fae.png">

<br>

그럼 권한이 없다고 나오는데 정상이다. 사용자를 만들어주면 된다.

* 참고로 사용자를 만들면,  **new_user_credentials.csv** 파일을 다운받을 수 있는데, 중요한 파일이니 잘 보관한다.

<br>

- IAM Role 부여

IAM - 액세스 관리 - 역할 탭으로 이동한다.  
역할 만들기를 눌러준다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 48 35" src="https://user-images.githubusercontent.com/81137234/225836446-f318bc27-553f-4f31-9e33-0a19014059ba.png">

<br>

이 계정(Root)의 권한을 IAM에 부여해주는 과정이기 때문에 다음과 같이 체크박스를 체크한다.  
Root 에서 MFA 2차 인증을 해주었기 때문에 MFA 체크박스를 눌러준다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 51 18" src="https://user-images.githubusercontent.com/81137234/225836562-4f42facc-d418-44fa-9cc0-7690106d8929.png">

<img width="600" alt="스크린샷 2022-05-17 오후 3 51 05" src="https://user-images.githubusercontent.com/81137234/225836580-178a31f4-9ee2-4b10-b69a-12809933d780.png">

<br>

IAMFULLAccess : 보통 인사팀에서 많이 사용하는 권한이라고 한다. IAM 계정의 생성, 삭제 등 인적자원 관리하는데 모든 권한을 가진 권한이다.  

PowerUserAccess : AWS 내에 모든 서비스에 대해 접근 가능하고 인스턴스 삭제, 생성 등을 할 수 있는 권한이다.  

참고로 Administator 권한은 말 그대로 admin 권한을 말하는데(admin = iamfullaccess + poweruseraccess 권한을 합친 최상위 권한이다. Root 바로 밑이라고 보면 된다)  

Admin 권한은 CTO 님만 설정하였고, biling을 담당하는 직원분에게는 bilingFullAccess 줬고,개발자들에게는 poweruseraccess 정도 줘서 개발하게 했다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 56 04" src="https://user-images.githubusercontent.com/81137234/225837129-88c2d6e1-3c2c-4a92-a88a-4b4fc5373607.png">

<br>

계속 다음 다음 눌러서 역할 생성을 누른다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 3 57 21" src="https://user-images.githubusercontent.com/81137234/225837468-eb556f85-aee6-4d7a-8161-ede63b850b45.png">

<br>

IAM - 액세스 관리 - 사용자 - 권한 부여할 계정 으로 들어온다.  
할당된 MFA 디바이스가 ****이미 세팅되어 있는데, MFA 디바이스 세팅을 할 것이다.  
MFA 세팅 버튼을 누르고 상위의 A Virtual MFA device 체크를 한다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 00 13" src="https://user-images.githubusercontent.com/81137234/225837712-371cd525-fccb-419c-9510-70a5e3ad1d44.png">

<br>

핸드폰으로 google OTP app을 설치받는다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 02 26" src="https://user-images.githubusercontent.com/81137234/225837806-839c7f01-c143-467d-8596-ad813320043a.png">

<br>

2번의 OTP 6자리 인증 코드 입력을 해야한다.  
첫번째 6자리 코드를 넣고 또 2번째 6자리 코드를 기다렸다가 넣는다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 02 58" src="https://user-images.githubusercontent.com/81137234/225838017-c18efbe6-355b-40b2-a32a-d96c5b8281a6.png">

<br>

그럼 MFA 디바이스 할당이 뜬다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 06 34" src="https://user-images.githubusercontent.com/81137234/225838252-eb79f9b4-9cf7-4d5e-9823-cdaa5d7ec7cb.png">

<br>

IAM - 사용자 - 권한부여한 사용자이름 이동해서 사용자 ARN을 복사한다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 05 02" src="https://user-images.githubusercontent.com/81137234/225838444-0f3ec605-a28a-4e73-abcc-dbb384f023f3.png">

<br>

IAM - 역할 - 설정한 역할이름입력 - 신뢰관계 탭으로 이동해서  
**“AWS” : 복사한 사용자 ARN**을 복붙한다.  
그럼 aws 권한 설정은 끝났다.  
이제 IAM 계정에 로그인해서 인증하는 과정을 거치면 끝난다.  

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 09 20" src="https://user-images.githubusercontent.com/81137234/225838626-ffcd5f81-92ab-43a4-8f36-07134e8a16a7.png">

<br>

IAM - 역할 - 그룹명입력 해서 콘솔 역할전환링크를 복사해 놓는다. iam 로그인 후 사용할 것이다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 14 17" src="https://user-images.githubusercontent.com/81137234/225838839-6239e659-fd06-4373-b703-f1c59f75e9c9.png">

<br>

iam 로그인을 할 시간이다.  
iam 계정 생성할 때, new_user_credentials.csv 파일을 다운받았을 것이다. csv 파일에서  
https://0000000000000.signin.aws.amazon.com/console 라는 데이터가 있을건데, ctrl + 클릭해서 들어간다.

<br>

<img width="400" alt="스크린샷 2022-05-17 오후 4 14 11" src="https://user-images.githubusercontent.com/81137234/225839155-42d2e2cd-fa7f-4fb4-9753-40aa7d4d687e.png">

<br>

iam 계정 생성했을 때 id, pw를 입력한다.

<br>

<img width="400" alt="스크린샷 2022-05-17 오후 4 18 35" src="https://user-images.githubusercontent.com/81137234/225839198-f8011bc1-b6f3-4664-8f69-c45b9822a3db.png">

<br>

그럼 google otp app을 열어서 aws iam 계정 로그인으로도 MFA 인증을 해준다.  
마지막으로 **콘솔 역할전환링크**를 복사해 놓은 것을 새 인터넷 창에 붙여놓으면, 인증 확인하겠냐는 창이 뜬다.   인증을 확인해준다.

<br>

<img width="600" alt="스크린샷 2022-05-17 오후 4 19 03" src="https://user-images.githubusercontent.com/81137234/225839328-c720c9ce-c9f1-4a16-a8fe-d635166428b1.png">

<br>

이렇게 iam 계정으로 로그인했을 때, 오른쪽 상단처럼 jihoon이라는 본인이 설정한 username이 제대로 나오면 성공한 것이다.

<br>
