### IoC(제어의 역전)
객체를 내부에서 선언하지 않고 밖에서 줄 수 있도록 생성자를 만듦(DI)
###### IoC 컨테이너
밑에 서술된 역할들을 개발자가 하는 것이 아닌 이 IoC가 해준다 
##### 역할
* 의존성 주입(Dependency Injection)
* Bean 관리
* 객체의 생명주기 관리
* 관점 지향 프로그래밍
##### DL과 DI
* DL은 저장소에 저장되어 있는 Bean에 접근하기 위해 컨테이너가 제공하는 API를 이용해 Bean을 lookup 하는 것
* DI는 각 클래스간 의존 관계를 Bean 설정 관계를 바탕으로 컨테이너가 자동 주입하는 것
> * setter
> * constructor
> * method
우리는 BeanFactory나 ApplicationContext 씀
ApplicationContextsms BeanFactory를 상속 받음
##### BeanFactory
빈을 생성하고 의존관계 설정하는 가장 기본전 IoC 컨테이너
##### ApplicationContext
BeanFactory 확장된 버전

별도의 정보를 참고하여 빈의 생성, 관계 설정 등의 제어를 총괄하는 것