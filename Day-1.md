# Region & Availability

Amazon EC2는 세계 각지의 여러 곳에서 호스팅되고 있습니다. 이 위치는 AWS 리전, 가용 영역, Local Zones, AWS Outposts 및 Wavelength Zone으로 구성됩니다.

- 각 리전은 개별 지리 영역입니다.
- 가용 영역은 각 리전 내에 있는 여러 격리된 위치입니다.

<br>

<img width="500" alt="스크린샷 2023-03-15 오후 12 43 50" src="https://user-images.githubusercontent.com/81137234/225203606-d38891ba-aa89-47ed-8ed5-e2a70208186f.png">

<br>

aws는 이렇게 많은 서비스를 [아시아](https://aws.amazon.com/ko/about-aws/global-infrastructure/regions_az/)에 제공하고 있다.  
어떤 국가에서 서비스를 지원하는 지 보고 싶다면, 링크를 클릭해서 확인해보면 된다.

<br>

<img width="500" alt="스크린샷 2023-03-15 오후 12 47 30" src="https://user-images.githubusercontent.com/81137234/225203666-24e61a3c-1aa1-4ffe-adaf-87349edbecad.png">

<br>

1. 데이터 거버넌스 및 법적 요구사항 준수: 데이터는 명시적인 허가 없이 리전을 벗어나지 않습니다.
2. 고객과의 근접성: 대기 시간 단축
3. 지역 내에서 사용 가능한 서비스: 일부 지역에서는 새로운 서비스와 새로운 기능을 사용할 수 없습니다
4. 가격: 가격은 지역마다 다르며 서비스 가격 페이지에서 투명하게 공개합니다.

<br>

<img width="500" alt="스크린샷 2023-03-15 오후 12 49 30" src="https://user-images.githubusercontent.com/81137234/225205144-bc405137-c88c-460c-a771-65431b261112.png">

<br>

1. 각 리전과 가용영역 설정(usually 3, min is 2, max is 6) 

- ap-southeast-2a
- ap-southeast-2b
- ap-southeast-2c

2. 가용영역은 재난에 대비해 분리되어 있습니다.
3. 각 가용영역은 분리되어 있지만, 서로를 연결할 수 있습니다.


<br>

<img width="500" alt="스크린샷 2023-03-15 오후 12 51 16" src="https://user-images.githubusercontent.com/81137234/225205464-66d0362f-75a3-4f8a-8b15-43d5c8181e09.png">

특정 서비스는 AWS 특정 리전에 국한되므로 잘 확인해서 설정해야한다.

---

자세한 블로깅은 [이 글](https://geabalseabal.tistory.com/99)을 참고한다.

<br>