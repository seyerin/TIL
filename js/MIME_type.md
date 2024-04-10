# MIME type

→ Multipurpose Internet Mail Extensions

오직 텍스트만 보낼 수 있었던 SMTP의 단점을 보완하여 메세지 내부에 다른 파일을 전송할 수 있도록 하는 전자메일 프로토콜

mime type으로 인코딩한 파일은 content-type필드를 헤더에 담게 되며, 이를 통해 전송된 자원의 형식을 명시할 수 있다

현재는 전자메일에 국한되지 않고 웹을 통해 여러 형태의 파일을 전송하는데 두루 쓰임

### **mime type를 사용하는 이유**

과거에는 아스키 문자로 이루어진 파일만을 전송하는 것을 전제로 데이터를 교환하는 시스템이 설계 됨

하지만 점점 네트워크를 통해 바이너리 파일을 전송하는 일이 잦아짐

인터넷을 통해 전송 가능한 문자는 오로지 아스키 표준이기 때문에 다른 데이터를 이오 변환하는 과정이 필요

따라서 바이너리 파일을 아스키 코드로 변환하는 과정(인코딩)과 이를 다시 바이너리 파일로 변환하는 과정(디코딩)이 추가 됨

초기에는 `uuencode` 방식을 사용했지만 단점이 존재 했기 때문에 이를 보강한 `MIME` 방식이 등장하게 됨

- mime 방식은 전송한 파일의 포맷에 대한 정보도 제공한다는 이점이 있다

### mime type의 구조

- 기본적으로 type / subtype의 구조를 가지고 있음
- type은 파일의 종류를 의미하며 subtype은 파일의 포맷을 의미한다
- application / json의 경우에는 application이라는 바이너리 파일 중 json 포맷의 파일을 의미하는 식별자로서 기능한다

### Content-type 와 mime type

Content-type는 http 통신을 통해 전달받은 요청의 header 내에서 해당 요청의 body에 든 데이터 타입에 대한 정보를 나타낸다

즉 request body에 들어가는 데이터 타입에 대한 정보를 header가 명시할 수 있는데 이 때 사용하는 필드를 Content-type라고 한다

Content-type과 mime type의 목적성은 데이터의 타입을 명시하는데 있지만

Content-type은 단순히 웹에 국한되어 사용되지만 miem type은 인터넷 프로토콜에서 사용되기 때문에 Content-type 보다 상위 개념이라 할 수 있다

한 마디로 HTTP request의 header에 있는 Content-type 필드에는 request body에 담긴 데이터의 mime type를 추가한다고 할 수 있다
