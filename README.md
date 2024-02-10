# MVC 패턴이란?
> 모델-뷰-컨트롤러(model–view–controller)는 소프트웨어 공학에서 사용되는 소프트웨어 디자인 패턴

1. 과거에는 View에 모든 비즈니스 로직까지 넣어 코드의 길이가 길어지고 유지보수가 힘들었으나  
최근에는 MVC모델은 코드를 3가지 형태로 나누어 개발을 하는 MVC가 기본적인 디자인패턴이 되어 사용되고 있다.
2. 사용자 인터페이스로부터 비즈니스 로직을 분리하여 비즈니스 로직을 쉽게 고칠 수 있는 애플리케이션이 된다.

## Model, View, Controller
![image](https://github.com/miraexhoi/study/assets/109408165/e36e5b17-2737-4a5d-8e0f-dbcb97bf3c1d)

### Model
> Data. 정보들의 가공을 책임지는 컴포넌트
- Data와 애플리케이션이 무엇을 할 것인지를 정의하는 부분 ( 내부 비즈니스 로직을 처리하기 위한 역할 )  
  즉, Model은 Controller가 호출을 하면 DB와 연동하여 사용자의 데이터와 연관된 비즈니스 로직을 처리하는 역할  
- 데이터 추출, 저장, 삭제, 업데이트 등의 역할 수행
  
**Model의 규칙**

- 사용자가 편집하기를 원하는 모든 데이터를 가지고 있어야 한다.
- View나 Controller에 대헤서 어떤 정보도 알지 말아야 한다.
- 변경이 일어나면, 변경 통지에 대한 처리방법을 구현해야만 한다.

### View
> 사용자에게 보이는 부분, UI (User Interface)를 의미
- View는 사용자에게 보여주는 화면(UI)이 해당  
- 사용자와 상호작용을 하며 컨트롤러로부터 받은 모델의 결과값을 사용자에게 화면으로 출력  
- 여러개의 View가 존재 가능, Model에서 받은 데이터는 별도로 저장 x

**View의 규칙**

- Model이 가지고 있는 정보를 따로 저장해서는 안된다.
- Model이나 Controller와 같이 다른 구성요소들을 몰라야 한다.
- 변경이 일어나면 변경 통지에 대한 처리방법을 구현해야만 한다.
- ⭐️ Model과 View는 서로의 존재를 몰라야 한다.

### Controller
> 모델과 뷰 사이를 이어주는 브리지(Bridge) 역할을 의미
- Controller는 Model과 View 사이를 이어주는 인터페이스 역할   
  즉, Model이 데이터를 어떻게 처리할지 알려주는 역할
- 사용자로부터 View에 요청이 있으면 Controller는 해당 업무를 수행하는 Model을 호출하고  
  Model이 업무를 모두 수행하면 다시 결과를 View에 전달하는 역할

**Controller의 규칙**

- Model이나 View에 대해서 알고 있어야 하며 변경을 모니터링 해야 한다.
