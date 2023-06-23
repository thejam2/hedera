# hedera

## 장점 (다른 블록체인과 차별점) 
-   거래당 약 US$0.0001의 명목 요율로 낮은 수수료로 신속한 거래를 제공합니다.
-   해시 그래프의 "포크 없음" 목표는 원장의 안정성과 연속성을 보장합니다.
-   에너지 효율적이고 유지 관리가 적은 시스템을 제공하므로 기업에 적합합니다.
-   [비잔틴 결함 허용](https://academy.binance.com/en/articles/byzantine-fault-tolerance-explained) (ABFT)는 분산 시스템의 위험인 DDoS 공격으로부터 네트워크를 안전하게 보호합니다.
-   합의 타임스탬프에 대한 투표는 자동화되어 비트코인의 경우와 같이 채굴자가 특정 거래의 우선 순위를 지정하는 것을 방지합니다.

Hedera는 블록체인을 생성하는 일반적인 블록 대신 **해시 그래프**를 활용하여 데이터를 저장하는 독특한 블록체인 프로젝트입니다.
해시그래프는 지루한 작업 증명을 계산할 필요가 없으며 초당 최대 XNUMX만 건의 트랜잭션을 처리합니다.
또한 비트코인 ​​거래를 확인하는 데 드는 에너지 집약적인 작업을 피하기 때문에 거래는 에너지 효율적입니다.

## 단점
- 상대적으로 최근에 개발된 기술이므로 일부 기술적 문제나 확장성 문제 발생할 수 있습니다.
- 기업과 기관을 대상으로 설계되었으며 이는 중앙화된 특성이 일부 사용자들에게 신뢰성 및 개인 정보 보호에 대한 의문을 제기할 수 있습니다.

## 어떤식으로 처리하는지 
### 기존 블록체인 구조
![2gsjgna1uruvUuS7ndh9YqVwYGPLVszbFLwwpAYXYX2xEhb98u6m4NDZmVQTMV2LEnXk81Ydn3EmiekaCSRvsa6Ga5LV5ftnh7SR5mfXE4TfXvXLsg.png](https://coinpan.com/files/attach/images/198/679/615/165/ecf97faf092e35d3f00a4aa78898d6dd.png)

일반 체인은 내 거래가 승인되기위해 한 블럭이 생성되서 내 거래 트랜잭션이 포함되길 기다림.
블록 다음 블록 순차적으로 생성.

**그리고, 블럭이 수년이 지나서 많아지면, 그 만큼 처리속도가 더 느려짐**
  
### Hedera는 DAG구조
![image.png](https://coinpan.com/files/attach/images/198/679/615/165/7dceca2f16905dc9c3470811b96916cf.png)

DAG는 매개체와 매개체의 트랜잭션이 다른 트랜잭션을 검증하는 구조라 (심지어 이걸 병렬로 수행)

**동시에 전달.**
**시간이 지날수록, 전달 매개체가 많아질수록 전파가 더 빠른 구조**

### 해시그래프 합의
Hedera는 블록체인 합의 메커니즘에 대한 더 빠르고 안전한 대안인 해시그래프 합의를 사용하는 유일한 공개 원장입니다. Leemon Baird Hedera의 공동 창립자이자 수석 과학자가 만든 Hashgraph는 악의적인 공격을 방지하기 위해 최고 수준의 보안을 보장하면서 거래를 효율적으로 검증합니다. Hashgraph는 오늘 초당 10,000개 이상의 트랜잭션으로 높은 처리량을 달성하고 가십 프로토콜 및 가상 투표에 대한 혁신적인 가십에서 몇 초 만에 짧은 대기 시간 최종성을 달성합니다. 합의에 도달하면 트랜잭션은 변경 불가능하며 모든 사람이 투명하게 볼 수 있도록 공개 원장에서 사용할 수 있습니다.

### 라이프사이클 (트랜잭션의 해시그래프 처리)
Hedera 생태계에서 트랜잭션의 해시그래프 처리는 클라이언트가 트랜잭션을 생성할 때 시작됩니다.    
트랜잭션이 생성되면 트랜잭션과 관련된 수수료를 지불하는 계정에 의해 최소한의 암호화 서명이 이루어집니다.
계정, 주제 또는 토큰에 대해 설정된 속성에 따라 추가 서명이 필요할 수 있습니다.
클라이언트는 거래 처리에 대해 지불할 의사가 있는 최대 수수료와 스마트 계약 운영을 위한 최대 가스량을 규정할 수 있습니다.   
필요한 서명이 거래에 적용되면 클라이언트는 거래를 Hedera 네트워크의 모든 노드에 제출합니다. 
수신 노드는 트랜잭션의 유효성을 확인하고(예를 들어, 지불 계정이 수수료를 지불하기에 충분한 잔액을 가지고 있는지 확인), 유효성 확인이 성공한 경우 트랜잭션을 이벤트에 추가하고 해당 이벤트를 다른 노드에 가십함으로써 합의를 위해 Hedera 네트워크에 트랜잭션을 제출합니다.
 
신속하게 해당 이벤트는 다른 모든 노드로 전송됩니다.
네트워크는 [가십 프로토콜에 대한 가십을](https://docs.hedera.com/hedera/core-concepts/hashgraph-consensus-algorithms/gossip-about-gossip) 통해 이 트랜잭션을 기하급수적으로 빠르게 수신합니다 .
이벤트(및 그 안의 트랜잭션)에 대한 합의 타임스탬프는 각 노드가 독립적으로 네트워크의 노드가 해당 이벤트를 수신한 시간의 중위수를 계산하여 계산합니다.
[합의 타임스탬프가 계산되는 방법에 대한 자세한 내용은 여기](https://docs.hedera.com/hedera/core-concepts/hashgraph-consensus-algorithms#section-fair-timestamps)  에서 확인할 수 있습니다.

### 공공 원장
Hedera는 누구나 읽고 쓸 수 있는 매우 안전한 분산형 데이터베이스인 공개 트랜잭션 원장입니다.
최신 상태만 유지되는 원장의 복사본이 각 노드에 저장됩니다.
분산된 합의 및 분산화의 핵심 개념은 공개 원장을 검증 가능한 정보 및 자산을 저장하는 가장 신뢰할 수 있는 방법으로 만듭니다.

### 네트워크 노드
공개 원장은 합의 및 미러 노드로 구성된 네트워크인 메인넷에 저장됩니다. 
현재 Hedera Governing Council에 의해 허가되고 운영되는 동안, 컨센서스 노드는 미래에 아무나 운영될 수 있는 [무허가 상태가 될 것입니다 .](https://hedera.com/hh-decentralization-of-consensus.pdf)

컨센서스 노드는 네트워크의 최신 상태를 저장하면서 트랜잭션의 유효성과 순서에 대해 합의합니다.
[미러 노드는](https://docs.hedera.com/hedera/core-concepts/mirror-nodes) 개발자에게 분석 및 탐색기를 위해 기록 데이터를 저장하고 쿼리할 수 있는 유연하고 비용 효율적인 방법을 제공합니다.

### 헤데라 네트워크 서비스
Hedera 네트워크 서비스는 계정 생성, 토큰 발행, 원장에 데이터 쓰기, 스마트 계약 호출 및 기타 기능을 허용하는 일련의 API입니다.  
각 API 호출에는 필요한 처리 및 스토리지에 따라 예측 가능한 [거래 수수료가 있습니다.](https://www.hedera.com/fees)
[Hedera SDK를 사용](https://docs.hedera.com/hedera/sdks-and-apis/sdks) 하면 JavaScript, Java 및 Go를 포함하여 선호하는 언어로 API에 쉽게 액세스할 수 있습니다.
[서비스 종류 링크](https://hedera.com/services)


### 분산형 애플리케이션
공개 원장을 사용하는 애플리케이션은 더 큰 투명성과 신뢰를 제공합니다.
이를 통해 아티스트에게 직접 비용을 지불하는 음악 스트리밍 서비스나 감사가 필요 없는 중개 광고 네트워크와 같은 완전히 새로운 기능이 가능해집니다.
종합적으로 이러한 애플리케이션은 보다 공정하고 안전하며 분산된 미래를 구축하기 위해 Hedera에 네트워크 효과를 생성합니다.

## 블록하고 트랜잭션을 어떻게 처리하는지

Hedera의 원장 아키텍처는 블록체인의 경우와 같이 직렬이 아닌 병렬입니다.
블록체인의 경우 트랜잭션이 함께 묶여 블록을 형성한 다음 기존 체인에 추가됩니다.
Hedera DAG에서 시스템은 데이터를 기존 데이터 위에 이벤트로 저장합니다.
이러한 방식으로 네트워크는 트랜잭션을 묶고 데이터를 순차적으로 기록하는 데 걸리는 시간을 단축하므로 더 빠르게 아카이브합니다.

## RPC
Hedera [JSON-RPC Relay는](https://github.com/hashgraph/hedera-json-rpc-relay) Ethereum JSON-RPC 표준을 구현하는 오픈 소스 프로젝트입니다. JSON-RPC 릴레이를 통해 개발자는 친숙한 Ethereum 도구를 사용하여 Hedera 노드와 상호 작용할 수 있습니다. 이를 통해 Ethereum 개발자와 사용자는 평소처럼 계약을 배포, 쿼리 및 실행할 수 있습니다. [상호작용 가능한 OpenRPC 사양](https://playground.open-rpc.org/?schemaUrl=https://raw.githubusercontent.com/hashgraph/hedera-json-rpc-relay/main/docs/openrpc.json&uiSchema%5BappBar%5D%5Bui:splitView%5D=false&uiSchema%5BappBar%5D%5Bui:input%5D=false&uiSchema%5BappBar%5D%5Bui:examplesDropdown%5D=false) 과 간단한 [끝점 목록을](https://github.com/hashgraph/hedera-json-rpc-relay/blob/main/docs/rpc-api.md) 확인하십시오 . Hedera JSON-RPC 릴레이 구현은 _베타 버전_ 이며 현재 제한된 기능을 제공하며 개발자만 사용할 수 있습니다.

### HBAR 소수 자릿수[](#hbar-decimal-places)
JSON RPC 릴레이는 HBAR을 반환할 때 18자리 소수점을 사용합니다. 결과적으로 이 값은 JSON RPC Relay에서만 활용되기 때문에 소수점 이하 18자리를 반환합니다. **`msg.value`** **`gasPrice`** Hedera API 목록과 이들이 반환하는 소수점 이하 자릿수는 [HBAR 페이지를](/hedera/sdks-and-apis/sdks/hbars) 참조하십시오 .

### 커뮤니티 호스팅 JSON-RPC 릴레이[](#community-hosted-json-rpc-relays)
커뮤니티의 모든 사용자는 애플리케이션이 스마트 계약을 배포, 쿼리 및 실행하는 데 사용할 수 있는 자체 JSON RPC 릴레이를 설정할 수 있습니다. 프리뷰넷, 테스트넷 및 메인넷의 엔드포인트는 관련 문서 또는 웹사이트에서 찾을 수 있습니다. 아래에서 커뮤니티에서 호스팅하는 Hedera JSON RPC 릴레이 목록을 찾을 수 있습니다. 호스팅된 JSON RPC 릴레이를 이 목록에 추가하려면 [Hedera 문서 GitHub 리포지토리](https://github.com/hashgraph/hedera-docs) 에서 문제를 여십시오 . 해당 인스턴스에 대한 제한 사항을 검토하려면 커뮤니티에서 호스팅하는 웹 사이트를 방문하십시오.



