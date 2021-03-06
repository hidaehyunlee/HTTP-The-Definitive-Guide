## 14장 :octopus: 보안 HTTP

### __14.1__ 　 HTTP를 안전하게 만들기　 `junslee`

1. 한국은 IT 보안 강국이다.(O / X)<br>

2. 다음과 같은 상황에서 필요한 보안 요소를 보기에서 고르시오.<br><br>
`---------------------------------- < 보기 > ----------------------------------`<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;`무결성`(데이터가 변조되지 않은 정보로 목적지에 도달하게 한다.) <br>
&nbsp;&nbsp;&nbsp;&nbsp;`기밀성`(클라이언트와 서버는 감청에 대한 걱정없이 서로 데이터를 주고 받을 수 있어야한다.)<br>
&nbsp;&nbsp;&nbsp;&nbsp;`인증`(HTTPS를 통해 웹사이트의 진위 여부를 확인할 수 있다.)<br>
&nbsp;&nbsp;&nbsp;&nbsp;`적응성`(현재 알려진 최선의 보안 방법을 지원해야 한다.)<br><br>
`-----------------------------------------------------------------------------`<br><br>
상황1) 서버와 클라이언트가 데이터를 주고 받을 때 데이터가 암호화 되지 않아서 해커들이 네트워크 길목에서 패킷을 감청하면 사용자가 입력한 정보가 노출되거나 패킷을 조작해서 가짜 정보를 전송 할 수 있다. `_________`<br><br>
상황2) SSLv2는 1995년에 출시된 상당히 노후된 프로토콜이다. 그래서 많은 취약점들이 나타났고 이제는 어떠한 웹 환경에서도 활용이 적합하지 않다. `_________`<br><br>
상황3) 와이파이가 웹사이트에 광고를 추가하거나, 대역폭을 절약하고자 이미지 품질을 저하시키거나, 읽는 기사의 내용을 변조할 수 있다. `_________`<br><br>
상황4) 와이파이 액세스 포인트를 운영하는 사람이 인증되지 않은 가짜 웹사이트를 브라우저에 보낼 수도 있다. `_________`<br><br>

<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
1. 한국은 IT 보안 강국이다. (X) <br>
=> 한국은 IT 인프라 강국은 맞지만 IT 보안 강국은 아니다. <br>

2. 상황1) 기밀성, 상황2) 적응성, 상황3) 무결성, 상황4) 인증 <br>

</div>
</details>
<br>

### __14.2__ 　 디지털 암호학　 `junslee`

1. 암호란 메시지를 인코딩하는 어떤 특정한 방법과 나중에 그 인코딩된 비밀 메시지를 디코딩하는 방법이다. (O / X)<br>
2. 키가 있는 암호에서 같은 입력 메시지가 같은 인코딩 기계를 통과하면 항상 같은 출력을 생산한다. (O / X)<br>
3. 디지털 계산 도래의 결과로 맞는 내용은 무엇일까요?
- 속도 및 기능에 대한 기계 장치의 한계에서 벗어남으로써, 복잡한 인코딩과 디코딩 알고리즘이 가능해졌다.
- 매우 큰 키를 지원하는 것이 가능해져서, 단일 암호 알고리즘으로 키의 값마다 다른 수조 개의 가상 암호 알고리즘을 만들어낼 수 있게 되었다. 

<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
1. 암호란 메시지를 인코딩하는 어떤 특정한 방법과 나중에 그 인코딩된 비밀 메시지를 디코딩하는 방법이다. (O)<br>
2. 키가 있는 암호에서 같은 입력 메시지가 같은 인코딩 기계를 통과하면 같은 출력을 생산한다. (X)<br>
=>  키가 있는 암호에서 같은 입력 메시지가 같은 인코딩 기계를 통과하더라도 키의 값에 따라 다른 출력을 생산한다.
3. 둘 다 맞는 내용입니다.

</div>
</details>
<br>

### __14.3-14.4__ 　 대칭키 암호법 + 공개키 암호법　 `mihykim`
- __다음 설명을 읽고 각각 어떤 암호방식에 대한 설명인지 맞춰주세요!__
    - 비밀키가 누설되면 안된다.　( 대칭키 / 공개키 )
    - 메세지의 인코딩은 누구나 할 수 있고, 메세지를 디코딩하는 능력은 소유자에게만 부여하는 방식이다.　( 대칭키 / 공개키 )
    - 이 암호방식은 보안프로토콜이 전 세계의 모든 컴퓨터 사용자에게 적용될 수 있도록 해주었다.　( 대칭키 / 공개키 )
    - 인코딩할 때 사용하는 키가 디코딩할 때 사용하는 키와 같다(e=d).　( 대칭키 / 공개키 )
    - ('소수와 관련이 있어야 된다'라는 식의 제한 없이) 보통 모든 키 값이 유효하다.　　( 대칭키 / 공개키 )
    - 이 암호화방식에 사용되는 알고리즘은 계산이 느린 경향이 있다.　( 대칭키 / 공개키 )
    - 발송자와 수신자가 서로 대화하려면 둘 다 공유키를 가져야 한다는 단점이 있다.　( 대칭키 / 공개키 )
    - N개의 노드가 있고, 각 노드가 상대 N-1과 은밀하게 대화를 나누려면 약 N²개의 비밀키가 필요하다.　( 대칭키 / 공개키 )
- __보기에서 알맞은 단어를 골라 빈 칸을 채워넣어 주세요__
    - `<보기>`<br>`대칭키 암호방식(Symmetric-key Cryptography)`, `공캐키 암호방식(Public-Key Cryptography)`, `열거공격(Enumeration Attack)`, `열개공격(Ten-way Attack)`
    - 실제로는 두 암호방식을 섞어서 사용하는 혼성 암호체계가 사용된다. 예를 들어 노드들 사이의 안전한 의사소통 채널을 수립할 때는 편리하게 `_________________`를 사용하고, 이렇게 만들어진 안전한 채널을 통해 이후의 나머지 데이터를 암호화할 때는  `_________________`하는 방식이 흔히 쓰인다.
    - 좋은 암호 알고리즘은 공격자가 코드를 크래킹(저장된 패스워드를 알아내는 해킹 기법)하려면 이 우주에 존재하는 모든 가능한 키 값을 시도해보는 것 외에 다른 방법이 없게 만든다. 이렇게 무차별로 모든 키 값을 대입해보는 공격을 `_________________`이라고 한다.
<br>

#### :lock: 먼저 푸신 분들을 위한 코너
- __튜링은 어떻게 독일군의 암호를 풀었나?__
    - 에니그마(Enigma)는 이론적으로 보안 수준이 대단히 높았다. 
    - 그러나 평문과 암호문이 서로 같은 알파벳이 될 수 없다는 치명적 약점이 있었다. (a => a (x))
    - 암호화되기 전의 평문에 대해 알면, 이 점을 이용해서 정답 후보 가운데 상당수를 빠르게 제거할 수 있었다.
    - 앨런 튜링은 이 성질을 이용해 암호 해독 기계인 '봄브'를 설계했다.
    - 현대에는 '기지 평문 공격'이라고 불리는 이 방법은 연합군 암호해독가들에게 유용하게 사용되었다. 
    - "독일은 연합군이 자신의 암호체계를 해독할 줄은 꿈에도 몰랐다고 한다. ... 독일은 전쟁 종료전까지 영국이 자신의 암호를 해독했다는 사실을 모른 채 전투에 임했다고 한다. 독일 스스로도 너무나 강력하여 아무도 뚫을 수 없다고 자평했던 '에니그마'때문에 2차 세계대전에서 패전한 것이다." [(더보기)](https://brunch.co.kr/@futurewave/155)
- __고급 암호화 표준 [AES](https://namu.wiki/w/AES)__
    - 비대칭키에 RSA가 있다면, 대칭키에는 AES
- :newspaper: __책에 소개된 포브스 벌금기사__ [_(2012.4.30)_](https://www.forbes.com/sites/ciocentral/2012/04/30/the-cybersecurity-market-and-dangers-of-u-s-export-law/#5f3b45613779)
    - 사이버 보안이 워낙 중요하다보니 미국에서는 정부 차원에서 관련 소프트웨어 수출까지 규제함
    - 일례로 2002년에 한국에 수출한 네오포인트라는 회사가 1.1억원어치 벌금쓰,,,
- :newspaper: __사이버보안 관련 최신기사__ [_(2020.8.9)_](https://www.forbes.com/sites/louiscolumbus/2020/08/09/cybersecurity-spending-to-reach-123b-in-2020/#7ed5805b705f)
    - 시장규모가 검-나검나 커짐,,, 145조원 수준
    - 클라우드 보안은 무려 33% 증가 예상

<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
- __다음 설명을 읽고 각각 어떤 암호방식에 대한 설명인지 맞춰주세요!__
    - 비밀키가 누설되면 안된다.　( `대칭키`,`공개키` )
    - 메세지의 인코딩은 누구나 할 수 있고, 메세지를 디코딩하는 능력은 소유자에게만 부여하는 방식이다.　( `공개키` )
    - 이 암호방식은 보안프로토콜이 전 세계의 모든 컴퓨터 사용자에게 적용될 수 있도록 해주었다.　( `공개키` )
    - 인코딩할 때 사용하는 키가 디코딩할 때 사용하는 키와 같다(e=d).　( `대칭키` )
    - ('소수와 관련이 있어야 된다'라는 식의 제한 없이) 보통 모든 키 값이 유효하다.　( `대칭키` )
    - 이 암호화방식에 사용되는 알고리즘은 계산이 느린 경향이 있다.　( `공개키` )
    - 발송자와 수신자가 서로 대화하려면 둘 다 공유키를 가져야 한다는 단점이 있다.　( `대칭키` )
    - N개의 노드가 있고, 각 노드가 상대 N-1과 은밀하게 대화를 나누려면 약 N²개의 비밀키가 필요하다.　( `대칭키` )
- __보기에서 알맞은 단어를 골라 빈 칸을 채워넣어 주세요__
    - `<보기>`<br>`대칭키 암호방식(Symmetric-key Cryptography)`, `공캐키 암호방식(Public-Key Cryptography)`, `열거공격(Enumeration Attack)`, `열개공격(Ten-way Attack)`
    - 실제로는 두 암호방식을 섞어서 사용하는 혼성 암호체계가 용된다. 예를 들어 노드들 사이의 안전한 의사소통 채널을 수립할 때는 편리하게 `공캐키 암호방식(Public-Key Cryptography)`를 사용하고, 이렇게 만들어진 안전한 채널을 통해 이후의 나머지 데이터를 암호화할 때는  `대칭키 암호방식(Symmetric-key Cryptography)`하는 방식이 흔히 쓰인다.
    - 좋은 암호 알고리즘은 공격자가 코드를 크래킹(저장된 패스워드를 알아내는 해킹 기법)하려면 이 우주에 존재하는 모든 가능한 키 값을 시도해보는 것 외에 다른 방법이 없게 만든다. 이렇게 무차별로 모든 키 값을 대입해보는 공격을 `열거공격(Enumeration Attack)`이라고 한다.
</div>
</details>
<br>

### __14.5__ 　 디지털 서명　 `daelee`
1. 디지털 서명은 메시지에 붙어있는 특별한 암호 체크섬이며, 대칭 공개키에 의해 생성된다. **(O / X)**

  

2. 디지털 서명이 포함된 메시지는 수정 및 변경이 불가능하다. (O / X)

   
3. 디지털 서명은 누구라도 서명의 검증을 할 수 있다. **(O / X)**

   

4. 천재해커 여름이 태리의 디지털 서명을 해킹해 손에 넣었다고 가정하자. 갈취한 서명을 다른 메시지에 첨부해 악용하는 것이 가능할까? **(O / X)**

  

5. (여러분은 지금부터 `슬기로운 판사`입니다) 

   돈이 급했던 현준은 준서에게 현금 500만원을 빌린 뒤 차용증을 작성하고 디지털 서명을 했다. 몇 달 뒤 준서는 돈을 갚지 않는다며 현준을 고소했고, 차용증을 증거로 제출했다. 현준은 분명 돈을 갚은 뒤 함께 차용증을 삭제했으며 증거로 제출된 차용증은 준서가 따로 복사해 둔 복사본이라고 주장한다. 누구의 말이 진실이든, 유일한 증거인 차용증의 디지털 서명은 검증되었다. 현준이 돈을 갚은 사실을 따로 입증할 수 없을 때, 당신은 어떤 판결을 내리겠습니까? **(현준 승 / 준서 승)**

   
<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
1. 디지털 서명은 메시지에 붙어있는 특별한 암호 체크섬이며, 대칭 공개키에 의해 생성된다. **(O / X)**

   > 정답 : **X**
   >
   > 디지털 서명은 메시지에 붙어있는 특별한 암호 체크섬이며, **비대칭 공개키**에 의해 생성된다. 개인 키는 오직 소유자만이 알고 있고, 개인 키를 갖고 있는 사용자만이 이 체크섬을 계산할 수 있다. 즉, 체크섬은 저자의 **개인 서명**처럼 동작한다.

2. 디지털 서명이 포함된 메시지는 수정 및 변경이 불가능하다. (O / X)

   > 정답 : X
   >
   > 서명 후에도 메시지 내용을 수정할 수 있다. 그러나, 수정 후에는 서명 검증에 실패하기 때문에 검증하는 사람은 수정 되었음을 확인할 수 있다. 
   >
   > 디지털 서명이 실현하고자 하는 것은 **변경 방지가 아니라, 문서에 변경 행위가 있었는지 아닌지를 검출하는 것**이다.
   >
   > 때문에 디지털 서명은 메시지의 위조를 방지한다. 검증에 실패한 메시지는 법적 효력이 사라지기 때문이다. 만약 공격자가 송신 중인 메시지를 수정했다면, 체크섬이 맞지 않게 된다. 체크섬은 개인 키와 관련되어 있기에, 공격자는 체크섬을 조작할 수 없다.

3. 디지털 서명은 누구라도 서명의 검증을 할 수 있다. **(O / X)**

   > 정답 : **O**
   >
   > 메시지를 서명자의 **개인 키**로 암호화하는 것이 **서명 작성**
   >
   > 그 암호문을 서명자의 **공개 키**로 복호화하는 것이 **서명 검증**이다.

4. 천재해커 여름이 태리의 디지털 서명을 해킹해 손에 넣었다고 가정하자. 갈취한 서명을 다른 메시지에 첨부해 악용하는 것이 가능할까? **(O / X)**

   > 정답 : **X**
   >
   > 서명만 잘라내서 다른 메시지에 첨부하는 것은 가능하지만, 서명 검증에는 실패할 것이다. 서명은 메시지에 따라 달라지기 때문에 재이용이 불가능하다.

5. (여러분은 지금부터 `슬기로운 판사`입니다) 

   돈이 급했던 현준은 준서에게 현금 500만원을 빌린 뒤 차용증을 작성하고 디지털 서명을 했다. 몇 달 뒤 준서는 돈을 갚지 않는다며 현준을 고소했고, 차용증을 증거로 제출했다. 현준은 분명 돈을 갚은 뒤 함께 차용증을 삭제했으며 증거로 제출된 차용증은 준서가 따로 복사해 둔 복사본이라고 주장한다. 누구의 말이 진실이든, 유일한 증거인 차용증의 디지털 서명은 검증되었다. 현준이 돈을 갚은 사실을 따로 입증할 수 없을 때, 당신은 어떤 판결을 내리겠습니까? **(현준 승 / 준서 승)**

   > 정답: **준서 승**
   >
   > 디지털 서명이 붙은 차용증은 완전히 파기하는 것이 불가능하다. 언제든지 복구/복사될 수 있기 때문이다. 현준이 돈은 갚았음을 입증하기 위해서는, 차용금액을 갚았다는 사실을 기록한 `영수증`에 해당하는 문서를 새로 만들고 준서에게 디지털 서명을 부탁했어야 한다. 
   >
   > 즉, 디지털 서명을 파기하는 것은 불가능하지만, 차용증의 본질적인 내용을 다른 행위(돈을 지불했다는 새로운 사실)로 무효화 시키는 것이다.

디지털 서명에 대한 재밌고 자세한 내용이 담긴 PPT [링크](http://www.parkjonghyuk.net/lecture/modernCrypto/lecturenote/chap09.pdf)를 첨부합니다!

</div>
</details>
<br>

### __14.6__ 　 디지털 인증서　 `daelee`
1. 누구나 디지털 인증서를 만들 수 있다 **(O / X)**



2. `X.509 v3` 인증서 디지털 인증서에 대한 전세계적인 단일 표준이다. **(O / X)**

 

3. 사용자가 HTTPS를 통한 안전한 웹 트랜잭션을 시작할 때, 최신 브라우저는 자동으로 접속한 서버에서 디지털 인증서를 가져온다. 만약 서버가 신뢰할 수 없는 인증서를 갖고 있다면, 보안 커넥션은 실패한다. **(O / X)**

 
<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
1. 누구나 디지털 인증서를 만들 수 있다 **(O / X)**

   > 정답 : **O**
   >
   > **누구나** 디지털 인증서를 만들 수 있지만, 널리 인정받는 `서명 권한`을 얻을 수 있는 것은 아니다.

2. `X.509 v3` 인증서 디지털 인증서에 대한 전세계적인 단일 표준이다. **(O / X)**

   > 정답 : **X**
   >
   > 디지털 인증서에 대한 전 세계적인 `단일 표준`은 없다. 그렇지만 오늘날 대부분의 인증서가 그들의 정보를 `X.509`라 불리는 표준화된 서식에 저장하고 있다.
   >
   > `X.509 v3` 인증서는 인증 정보를 파싱 가능한 필드에 넣어 구조화하는 표준화된 방법을 제공한다. 

3. 사용자가 HTTPS를 통한 안전한 웹 트랜잭션을 시작할 때, 최신 브라우저는 자동으로 접속한 서버에서 디지털 인증서를 가져온다. 만약 서버가 신뢰할 수 없는 인증서를 갖고 있다면, 보안 커넥션은 실패한다. **(O / X)**

   > 정답 : **X**
   >
   > 브라우저는 서명 기관을 신뢰해야 할지 확신할 수 없다면 **대화 상자를 띄워 사용자에게 묻는다.** 서버가 디지털 인증서를 갖고 있지 않은 경우에 보안 커넥션에 실패한다.

</div>
</details>
<br>

### __14.7__ 　 HTTPS의 세부사항　 `hylee`
1. 해당 보안 계층에 들어갈 내용을 적고 1~5번 중에서 알맞은 위치를 찾아주세요!
    ![HTTPS_문제](https://user-images.githubusercontent.com/44167177/91932764-124e1700-ed22-11ea-8e12-9b6270e260d8.JPG)

2. 클라이언트가 URL을 검사했을 때 https 스킴을 갖고 있다면 그 뒤로 따라올 클라이언트와 서버간의 행동으로 옳은 것을 모두 고르시오

    a. 클라이언트는 서버에 80번 포트로 연결한다.
    
    b. 클라이언트는 서버와 Base-64 로 인코딩 된 몇몇 SSL 보안 매개 변수를 교환하면서 '핸드셰이크'를 한다.
    
    c. 암호화된 HTTP 명령이 뒤를 잇는다.
    
    
3. 다음 1 ~ 4번을 올바른 순서로 배열하시오

    (1) 클라이언트와 서버는 서로에게 암호화를 시작한다고 말해준다.
    
    (2) 서버는 선택된 암호와 인증서를 보낸다.
    
    (3) 클라이언트가 비밀정보를 보낸다. 클라이언트와 서버는 키를 만든다.
    
    (4) 클라이언트가 암호 후보들을 보내고 인증서를 요구한다.
    
4. 서버 인증서에 관한것으로 옮은 것을 모두 고르시오

      a. 브라우저는 신뢰할만한 CA 간접적으로 서명한 인증서도 받아들일 수도 있다
      
      b. 보안 HTTPS 트랜잭션은 클라이언트 인증서를 항상 요구한다
      
      c. 가상 호스트되는 사이트 인증서 관리는 까다로운 경우가 많다

<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">
  
1. 해당 보안 계층에 들어갈 내용을 적고 1~5번 중에서 알맞은 위치를 찾아주세요!
    > 정답 : SSL 혹은 TLS , 2 번

2. 클라이언트가 URL을 검사했을 때 https 스킴을 갖고 있다면 그 뒤로 따라올 클라이언트와 서버간의 행동으로 옳은 것을 모두 고르시오
    > 정답 : c 


    a. 클라이언트는 서버에 <b>443번</b> 포트로 연결한다.
    
    b. 클라이언트는 서버와 <b>바이너리 포맷으로 된</b> 몇몇 SSL 보안 매개 변수를 교환하면서 '핸드셰이크'를 한다.
        
    c. 암호화된 HTTP 명령이 뒤를 잇는다. (O)

    
3. 다음 1 ~ 4번을 올바른 순서로 배열하시오

    > 정답 : 4 - 2 - 3 - 1

    (1) 클라이언트와 서버는 서로에게 암호화를 시작한다고 말해준다.
    
    (2) 서버는 선택된 암호와 인증서를 보낸다.
    
    (3) 클라이언트가 비밀정보를 보낸다. 클라이언트와 서버는 키를 만든다.
    
    (4) 클라이언트가 암호 후보들을 보내고 인증서를 요구한다.
    
    ![image](https://user-images.githubusercontent.com/44167177/91934809-34966380-ed27-11ea-9541-4c403b8aa0cd.png)

    
    
4. 서버 인증서에 관한것으로 옮은 것을 모두 고르시오
 
      > 정답 : a, c

      a. 브라우저는 신뢰할만한 CA 간접적으로 서명한 인증서도 받아들일 수도 있다. (O)
      
        만약 신뢰할 만한 CA가 ‘샘의 서명 가게’를 위한 인증서에 서명을 하고 샘의 서명
        가게는 어떤 사이트 인증서에 서명을 한다면， 브라우저는 그 인증서를 올바른 CA
        경로에서 파생된 것으로 보고 받아들일 수 있다.
      
      b. 보안 HTTPS 트랜잭션은 <b>클라이언트 인증서(x) => 서버 인증서(O)</b>를 항상 요구한다 
       
       웹 서버는 클라이언트 인증서를 요구할 수 있지만, 실제로는 좀처럼 일어나지 않는일이다
       한편， 보안 HTIPS 트랜잭션은 항상 서버 인증서를 요구한다. 누군가가 웹 서버에 
       신용카드 정보를 보내는 것과 같은 보안 트랜잭션을 수행할 때, 그는 대화중인 조직이
       그와 대화하고 있다고 생각한 그 조직이 맞는지 알고 싶을 것이다.
      
      c. 가상 호스트되는 사이트 인증서 관리는 까다로운 경우가 많다 (O)
      
        사용자가 사이트에 접속했을 때, 서버 인증서에 나열된 공식 호스트과 사용자가 브라우징 했던 가상 호스트 명이
        맞지 않은 경우 경고를 띄어준다. 이러한 문제를 피하기 위해 사이트의 소유자는 보안 트랜잭션을 시작히는
        모든 시용자를 공식호스트명이 붙은 사이트로 리다이렉트 하게한다.

</div>
</details>
<br>

### __14.8__ 　 진짜 HTTPS 클라이언트　 `jehong`

#### 다음 보기를 참고해서 빈칸을 채우세요.

> 중복 가능
>
> 숫자는 보기에 없음
>
> 문제가 그림과 관련이 없을 수도 있음


<img src="https://images.velog.io/images/jehjong/post/bdd93fe7-64d7-4d68-aa9b-0d0b17941aec/image.png" width="650" />


> **<보기>**
>
> `gethostbyname()`, `SSL_connect()`, `SSL_set_fd()`,  `SSL_new()`, `SSL_write`,  `DES-CBC3-MD5`, `RSA Data Security`, `보안`, `clients1.online.msdw.com`, `TCP 커넥션`, `IP주소`, `OpenSSL`

 

1. `_____________` 은/는 SSL 클라이언트와 서버 프로그래밍을 쉽게 만들어주는, SSL과 TLS의 가장 인기 있는 오픈 소스 구현이다. 
2. 위에서 요청에 대응하는 호스트 명은 `_____________` 이다.
3. 2)번의 IP 주소는 `_____________` 함수를 이용해 입력 호스트 명을 변환한 것이다.
4. `__`(숫자) 단계가 완료된 후 SSL 커넥션으로 보안 데이타 전송을 할 준비가 된다.
5. SSL 핸드셰이크는 SSL 스택을 소켓에 붙이고 `_____________` 를 호출해 수행된다.
6. 클라이언트와 서버는 `_____________` 대량 암호화 암호를 쓰는 것으로 합의했다. 
7. 위에서 발급된 인증서는 `_____________` 에 의해 승인되었다.
8. OpenSSL이 아닌 진짜 SSL 애플리케이션은 `__`(숫자) 단계에서 인증서에 대한 기본적인 검사를 한다.
9. 7번은 한번 SSL 채널이 수립된 후 클라이언트가 `_____________` 채널을 통해 보낸 자신의 HTTP 요청이다.



<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">

#### 다음 보기를 참고해서 빈칸을 채우세요.

> 중복 가능
>
> 숫자는 보기에 없음
>
> 문제가 그림과 관련이 없을 수도 있음


<img src="https://images.velog.io/images/jehjong/post/bdd93fe7-64d7-4d68-aa9b-0d0b17941aec/image.png" width="650" />


> **<보기>**
>
> `gethostbyname()`, `SSL_connect()`, `SSL_set_fd()`,  `SSL_new()`, `SSL_write`,  `DES-CBC3-MD5`, `RSA Data Security`, `보안`, `clients1.online.msdw.com`, `TCP 커넥션`, `IP주소`, `OpenSSL`

 

1. `OpenSSL` 은/는 SSL 클라이언트와 서버 프로그래밍을 쉽게 만들어주는, SSL과 TLS의 가장 인기 있는 오픈 소스 구현이다. 
2. 위에서 요청에 대응하는 호스트 명은 `clients1.online.msdw.com` 이다.
3. 2)번의 IP 주소는 `gethostbyname()` 함수를 이용해 입력 호스트 명을 변환한 것이다.
4. `6`(숫자) 단계가 완료된 후 SSL 커넥션으로 보안 데이타 전송을 할 준비가 된다.
5. SSL 핸드셰이크는 SSL 스택을 소켓에 붙이고 `SSL_connect()` 를 호출해 수행된다.
6. 클라이언트와 서버는 `DES-CBC3-MD5` 대량 암호화 암호를 쓰는 것으로 합의했다. 
7. 위에서 발급된 인증서는 `RSA Data Security` 에 의해 승인되었다.
8. OpenSSL이 아닌 진짜 SSL 애플리케이션은 `6`(숫자) 단계에서 인증서에 대한 기본적인 검사를 한다.
9. 7번은 한번 SSL 채널이 수립된 후 클라이언트가 `보안` 채널을 통해 보낸 자신의 HTTP 요청이다.

</div>
</details>
<br>

### __14.9__ 　 프락시를 통한 보안 트래픽 터널링　 `taelee`

![image](https://user-images.githubusercontent.com/55867479/92004376-1fe4ba80-ed7d-11ea-92e9-4f4a27768249.png)

#### 1. 프락시는 클라이언트의 역할을 대신하여 서버와 통신을 한다. 평생 클라이언트의 요청을 대신해서 서버에게 퍼나르던 프락시는 클라이언트를 친구라고 생각했다. 하지만 어느날 클라이언트는 프락시를 쏙 빼고 서버랑만 HTTPS 암호화를 하기로 해서 프락시는 기분이 안좋아졌다. 왜일까?

1. 서버와 클라이언트가 프락시빼고 암호화하기로 결정했기 때문에
2. 프락시와 제일 가깝다고 생각했던 클라이언트가 서버랑만 암호화 하기로 결정해서
3. 클라이언트와 서버가 서로 주고받는 메세지를 매일 훔쳐보던 프락시는 더 이상 메세지를 훔쳐볼 수 없어졌기 때문에
4. 매일 메세지를 훔쳐보던게 걸린 줄 알고 제발 저려서
5. 샤브샤브를 싫어해서 샤브샤브 식당 안 간다고 한 적이 있는데 마지못해 식당을 가보니 너무 맛있어서 입장이 난처해져서

#### 2. 너무 상심한 프락시는 클라이언트에게 파업을 선언했다.
#### "메세지를 모두 암호화해버려서 누구한테 보내는지도 모르는데 앞으로 어떻게 너희들의 메세지를 전달해줄 수 있겠어? 이제 연락하지마!"
#### 이를 달래기 위해(그리고 일을 시켜야하니깐) 클라이언트는 아주 조금 메세지에 대한 정보를 알려주기로 했다. 그 정보는 다음 중 무엇인가?(중복가능)

1. 서버가 어디에 있는지 알려준다.(CONNECT로 시작하는)
2. HTTP버전이 무엇인지 알려준다.
3. 클라이언트가 앞으로 프락시랑 더 친하게 지낼것이라는 내용의 편지가 있는 장소를 알려준다.
4. 0개 이상의 HTTP 요청 헤더들을 알려준다.
5. 그 동안 프락시가 메세지를 매번 훔쳐봐서 갑갑했다고 써놓은 일기장의 위치를 알려준다.

#### 3. 메세지의 일부를 알려주기로한 클라이언트의 제안을 듣고 프락시는 파업을 철회했다. 다시 열심히 클라이언트와 서버 사이의 메세지를 대신 전달하는 역할을 하기로 한 프락시는 서버로부터의 응답을 클라이언트에게 가져다 줄 때 이전과는 다른 응답메세지를 보내게 되었다. 그 메세지는 무엇인가? 

#### 4. 이 일을 계기로, 대신 열심히 일해주는 프락시의 **노고**를 치하하기 위해 프락시가 하고 있는 이 일련의 과정에 대해 이름을 붙였다. 그 이름은?

   


<details>
<summary> <b> :page_facing_up: 답지 </b>  </summary>
<div markdown="1">

#### 1. 프락시는 클라이언트의 역할을 대신하여 서버와 통신을 한다. 평생 클라이언트의 요청을 대신해서 서버에게 퍼나르던 프락시는 클라이언트를 친구라고 생각했다. 하지만 어느날 클라이언트는 프락시를 쏙 빼고 서버랑만 HTTPS 암호화를 하기로 해서 프락시는 기분이 안좋아졌다. 왜일까?

1. 서버와 클라이언트가 프락시빼고 암호화하기로 결정했기 때문에
2. 프락시와 제일 가깝다고 생각했던 클라이언트가 서버랑만 암호화 하기로 결정해서
3. **클라이언트와 서버가 서로 주고받는 메세지를 매일 훔쳐보던 프락시는 더 이상 메세지를 훔쳐볼 수 없어졌기 때문에**
4. 매일 메세지를 훔쳐보던게 걸린 줄 알고 제발 저려서
5. 샤브샤브를 싫어해서 샤브샤브 식당 안 간다고 한 적이 있는데 마지못해 식당을 가보니 너무 맛있어서 입장이 난처해져서

#### 2. 너무 상심한 프락시는 클라이언트에게 파업을 선언했다.

#### "메세지를 모두 암호화해버려서 누구한테 보내는지도 모르는데 앞으로 어떻게 너희들의 메세지를 전달해줄 수 있겠어? 이제 연락하지마!"
#### 이를 달래기 위해(그리고 일을 시켜야하니깐) 클라이언트는 아주 조금 메세지에 대한 정보를 알려주기로 했다. 그 정보는 다음 중 무엇인가?(중복가능)

1. **서버가 어디에 있는지 알려준다.(CONNECT로 시작하는)**
2. **HTTP버전이 무엇인지 알려준다.**
3. 클라이언트가 앞으로 프락시랑 더 친하게 지낼것이라는 내용의 편지가 있는 장소를 알려준다.
4. **0개 이상의 HTTP 요청 헤더들을 알려준다.**
5. 그 동안 프락시가 메세지를 매번 훔쳐봐서 갑갑했다고 써놓은 일기장의 위치를 알려준다.

#### 3. 메세지의 일부를 알려주기로한 클라이언트의 제안을 듣고 프락시는 파업을 철회했다. 다시 열심히 클라이언트와 서버 사이의 메세지를 대신 전달하는 역할을 하기로 한 프락시는 서버로부터의 응답을 클라이언트에게 가져다 줄 때 이전과는 다른 응답메세지를 보내게 되었다. 그 메세지는 무엇인가? 

**Connetion Established**

#### 4. 이 일을 계기로, 대신 열심히 일해주는 프락시의 **노고**를 치하하기 위해 프락시가 하고 있는 이 일련의 과정에 대해 이름을 붙였다. 그 이름은?

**터널링**

</div>
</details>
<br>
