# hexagonal-architecture


- 전통적인 layered architecture 와 hexagonal architecture와의 비교
- layered architecture 
    - ![layered_architecture](./image/layered_architecture.png)
    - 상위 레이어는 하위 레이어와 상호 작용할 수 있지만 반대 방향으로는 상호 작용할 수 없음
    - application layer와 domain layer 는 hexagonal architecture 와 동일한 역할을 함
    - UI layer와 database layer 는 hexagonal architecture 의 동작 방식과 차이가 있음 

- hexagonal architecture
    - ![hexagonal_architecture](./image/hexagonal_architecture.png)    
    - domain model
        -  모든 비즈니스 결정이 이루어지는 비즈니스 로직이있는 곳
        -  비즈니스 자체가 변경되지 않는 한, 가장 적게 변경 될 수 있는 소프트웨어의 가장 안정적인 부분
        
    - application service : 클라이언트가 도메인 모델과 상호 작용하는 파사드 역할을 한다
        - stateless
            - 클라이언트와 상호작용하면서 변경될 수 있는 상태를 유지하지 않는다
            - operation 을 실행하기 위한 정보는 application service 메소드의 인풋 파라미터로 들어가야 한다 
        - 시스템 보안을 강화한다
            - 인가된 요청인지를 확인하는 작업을 application service 에서 하는게 좋다
        - DB 트랜잭션 제어
            - application service method 가 하나의 트랜잭션을 형성해야 한다(성공시 commit, 실패시 rollback)
            - 같은 트랜잭션이 여러개의 application service에 걸쳐 있다면, domain service로의 분리도 생각해볼 필요가 있다
        - orchestration
            - business logic을 포함하지 않는다. 단지 business operation 을 조정할 뿐이다
        
        
         
    
    
    
    