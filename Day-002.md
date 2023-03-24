# IAM User & Group

루트계정은 정말 필요할 때만 사용하는 것이 좋고, 보안을 위해서는 IAM 관리자 계정을 사용하는 것이 좋다.  
기본적인 IAM 계정 생성을 알아보자.

<br>

![스크린샷 2023-03-16 오후 5 57 57](https://user-images.githubusercontent.com/81137234/225566790-04021170-f5b9-4e17-92ce-940a45402dfe.png)

<br>

사용자 추가를 눌러 계정을 만든다.

<br>

![스크린샷 2023-03-16 오후 6 04 46](https://user-images.githubusercontent.com/81137234/225567554-8189a718-392a-45e1-b550-6b95d84fbb9a.png)

<br>

![스크린샷 2023-03-16 오후 6 05 49](https://user-images.githubusercontent.com/81137234/225567788-dfa37378-1b53-49eb-b646-81f38ddd848e.png)

<br>

그룹을 생성하고 그 그룹에 사용자를 넣자.

<br>

![스크린샷 2023-03-16 오후 6 06 44](https://user-images.githubusercontent.com/81137234/225568037-8916dcaa-504b-4f70-8ff3-8c90326ba895.png)

<br>

admin 그룹에 속한 모든 사용자에게 administratorAccess 권한을 주겠다.  
참고로 이 권한은 IAM 권한 + AWS Service 권한이 다 있는 총관리자 권한이라고 보면 된다.  

<br>

<img width="383" alt="스크린샷 2023-03-16 오후 6 10 31" src="https://user-images.githubusercontent.com/81137234/225569173-838d4420-46a5-44c7-a642-cee1531137a9.png">

<br>

만든 계정으로 로그인을 해보자

<br>

![스크린샷 2023-03-16 오후 6 12 17](https://user-images.githubusercontent.com/81137234/225569797-f47b0111-8b5f-4eb5-83f5-39ac4139bb37.png)

<br>

계정의 Account Alias가 000000001 처럼 나올것이다.  
보안을 위해서 이것도 변경하자.

<br>

