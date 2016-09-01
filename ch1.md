## 빨강색 알약을 받아먹다

Elixir programming language 는 immutable state 가 있는 functional programming 그리고 concerrency 에 대한 actor 기반의 접근을 깔끔하고 모던한 syntax 로 wrap 한 것이다. 그리고 industrial-strength / high-performance / distributed (분산) 인 Erlang VM 위에서 돌아간다. 그런데 그런 말이 다 무슨 뜻인지?

그 뜻은 우리의 소중한 시간을 잡아먹는 어려운 문제에 대해 상당한 부분 이제는 걱정을 그만둬도 좋다는 뜻이다. 이제 더이상 multithreaded environment 아래에서 data consistency 를 어떻게 유지할까 하는 생각을 별로 힘들여서 할 필요가 없다. 이제는 scaling 에 별로 신경이 쓰이지 않는다. 그리고 무엇보다 중요한 것은, 우리는 이제 programming 을 다른 시각으로 보게 된다.. 그런 뜻이다.

### programming 은 transforming data 에 대한 것이어야 한다

object-oriented 나라에서 오신 분이라면 아마도 classes and their instances 의 입장에서 생각하는 버릇이 들어 있을 것이다. class 에는 behavior 가 정의되고 object 에는 state 가 보관된다. 개발자는 나비를 연구하는 분류생물학자와도 같이 근엄하게 앉아서 their problem 을 model 할 수 있는 class 들의 얼키고 설킨 hierarchies (위계) 를 해결하는 데에 시간을 바친다.

objects 로 code 할 때에 우리는 state 에 대하여 생각하고 있다. 우리의 모든 시간은 objects 안의 methods 를 call 하고 other objects 로 그들을 pass 하는 데에 들어간다. 여기서는 class 가 왕이다. 각 instance 가 할 수 있는 것을 모두 정의하며 instance 가 보관하는 state of the data 를 implicitely control 한다. 우리의 목적은 하나, data-hiding 이다.

하지만 현실의 세상은 그와 다르다. 현실의 세상은 abstract hierarchies 을 model 하는 일을 원치 않는다 (그 이유는 왜냐하면 진짜로 hierarchies 에 해당하는 것은 현실에 별로 없다) 우리는 get things done 을 원하고 maintain state 를 원하지 않는다.

지금 당장, 예를 들어서 내가 empty computer files 를 files containing text 로 transform 한다고 하자. 얼마 되지 않아 여러분이 읽을 수 있는 format 으로 나는 그 파일을 transform 할 것이다. 어딘가에 있을 web server 가 다운로드 하겠다는 여러분의 request 를, 그 책이 들어 있는 HTTP response 로 transform 한다.

나는 hide data 를 원치 않는다. 나는 transform data 를 원한다. 

### transformation 과 pipeline 의 조합

### functions 는 data transformers 이다

### Elixir 설치

이 책에서는 Elixir 1.2 를 대상으로 한다. 가장 최근 업데이트한 instruction 은 [http://elixir-lang.org/install.html](http://elixir-lang.org/install.html) 에 가면 확인할 수 있다. 지금 가서 설치하자. 

### Elixir 실행

이 책에서 terminal session 은 다음과 같이 나타낸다.

```
$ echo Hello, World
Hello, World
```

