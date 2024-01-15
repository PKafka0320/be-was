# java-was-2023

Java Web Application Server 2023

## 프로젝트 정보 

이 프로젝트는 우아한 테크코스 박재성님의 허가를 받아 https://github.com/woowacourse/jwp-was 
를 참고하여 작성되었습니다.

## 학습 내용

### MIME type

https://developer.mozilla.org/ko/docs/Web/HTTP/Headers/Content-Type
https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/MIME_types

Content-Type 헤더는 리소스의 media type을 나타내기 위해 사용됩니다.<br>
여기서 media type 이란 MIME type을 말하는데, 응답에 보내는 파일의 
형식에 맞는 타입으로 지정해주어야 호스트가 정상적으로 정상적으로 사용할 수 있습니다.

### Java Thread Model

https://www.baeldung.com/java-threading-models
https://e-una.tistory.com/70

자바 스레드 모델은 매핑 방법에 따라 3 가지가 있습니다.

#### Many-to-One Model

다대일 모델은 여러 사용자 스레드를 하나의 커널 스레드에 매핑하며, 
스레드는 사용자 공간의 스레드 라이브러리에 의해 관리됩니다.

한 스레드가 blocking 되는 경우 전체 프로세스가 block 되며, 한 번에 하나의 스레드만이 커널에 접근할 수 
있기 때문에 멀티 코어 시스템에서 병렬로 실행될 수 없습니다.<br>
하지만 동기화 및 리소스 공유가 쉽기 때문에 실행 시간이 단축된다는 장점이 있습니다.

Java 의 초기 버전의 스레드 모델인 Green Thread 가 이 모델을 사용했으며, 
대부분의 컴퓨터 시스템에서 멀티 코어가 표준이 되면서 그 이점을 살릴 수 없기 때문에 현재는 사용되지 않습니다.

#### One-to-One Model

일대일 모델은 각 사용자 스레드를 각각 하나의 커널 스레드에 매핑합니다. 
따라서 하나의 스레드가 Blocking 되더라도 다른 스레드는 계속 실행되기 때문에 병렬 실행이 용이합니다.

하지만 사용자 스레드를 만들기 위해 커널 스레드를 만들어야 하며, 많은 수의 커널 스레드는 시스템 성능에 부담을 
줄 수 있기 때문에 윈도우나 리눅스는 스레드 수의 제한을 둡니다.

#### Many-to-Many Model

다대다 모델은 여러 개의 사용자 스레드를 그보다 적거나 같은 수의 커널 스레드로 멀티플렉스합니다.<br>
커널 스레드의 수는 응용 프로그램에 따라 다르며, 코어의 수가 많을 수록 많은 커널 스레드를 할당받습니다.

다대다 모델은 다대일 모델과 일대일 모델의 단점을 절충한 방법으로, 필요한 만큼 사용자 스레드를 생성하고 
그에 상응하는 커널 스레드가 병렬로 수행될 수 있습니다.<br>
또한 가장 높은 정확도의 동시성 처리를 제공하는 모델로, 하나의 스레드가 blocking 되었을 경우 커널은 
다른 스레드의 작업을 수행할 수 있습니다.
