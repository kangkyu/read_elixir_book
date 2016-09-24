1부 언어

책의 앞부분 은 Elxir 언어에 대한 소개이다. Elixir 와 Erlang 에 대한 high-level overview 를 선보이는 것으로 출발한다. 두 가지 technologies 에 대한 goals and benefits 를 의논하는 것이다. 2장 에서는 Elixir 언어의 basic building blocks 를 배운다. module 이라든가 functions, type system 등 이다. 3장 에서는 pattern-matching 의 treatment 그리고 control-flow 의 상용 표현에 대해서 상세히 서술한다. 4장 에서는 immutable data structure 를 가지고 higher-level data abstrations 을 implement 하는 법을 배운다.

1 첫 steps

1.1 Erlang 에 대하여

?
asdf install elixir 1.0.5

1.2 Elxir 에 대하여

2 Building blocks

Elixir 를 배울 시간이다. 이 장에서는 module 이라든가 functions, type system 등 기본 building blocks 에 대하여 소개한다. 길고 지루한 여정이 되겠지만 그래도 language features 를 접하는 것은 중요하고 더 흥미롭고 고위의 주제를 다루기 위한 준비이다.

출발하기 전에 Elixir version 1.0.x (Erlang 17.x 가 또한 필요함) 를 설치한다. 공식 Elixir 의 업뎃 되어 있는 방법을 따르는 것이 제일 좋겠다. 그 과정이 클리어 되었다면 Elixir 의 여행을 떠나자. interactive shell 을 아는 것이 첫번 주제이다.

documentation
http://elixir-lang.org/docs/stable/elixir

crash course
http://elixir-lang.org/crash-course

2.1 interactive shell

시험해 보고 언어의 특성을 배우는 데 가장 단순한 길은 interactive shell 이다. command line 에서 `iex` 를 실행하면 Elixir interactive shell 이 나온다.

```
$ iex
...

iex(1)>
```

`iex` 를 실행함으로써 BEAM 의 instance 를 시작하고 나서 interactive Elixir shell 을 그 안에서 시작한다. Runtime 정보가 print 되고 그래서 Erlang 과 Elixir 의 version 이라든가 하는.. 그런 다음 prompt 가 나오고 이제 Elixir 표현을 입력할 수 있다.

```
iex(1)> 1 + 2   <- Elixir expression
3               <- result of expression
```

표현을 하나 타이프 한 뒤에 보면 그것은 interpreted and executed 해석 되고 집행 된다. 그 return value 내놓은 값이 화면에 print 된다.

NOTE: 모든 것이 다 return value 를 갖는다. function calls 만이 아니고 if 나 case 같은 "constructs" 도 해당한다.

실용적으로 말해서 유효한 Elxir code 가 된다고 하면 무엇이나 다 타이프 할 수 있다. 더 복잡한 여러 줄 되는 표현도 가능하다.

```
iex(2)> 2 * (
...(2)>   3 + 1   <- expression isn't finished
...(2)> ) / 4     <- expression is finished, so it's evaluated
2.0
```

세미콜론으로 분리해 주면 한 줄에 둘 이상의 표현을 넣을 수 있는데 그런 경우에는

```
iex(3)> 1 + 2; 1 + 3
4                 <- 마지막 표현의 결과가 나온다.
```

이러한 규칙이 shell 에 뿐만 아니라 표준적인 Elixir code 에도 적용한다는 것을 기억할 것. 언급한 대로 source code에서 유효한 것은 무엇이든 웬만하면 shell 에서 작동한다.

shell 을 끝내는 방법은 Ctrl+C 를 두번 누르면 된다. 그 방법은 OS process 와 모든 background jobs 를 모두 강제로 종료한다. 그래도 대개는 shell 을 사용하는 경우가 real production systems 가 아니기 때문에 상관 없지만, 좀더 예의바른 방법을 원한다면 System.halt 를 부른다.


iex(4)> h
iex(5)> h IEx
