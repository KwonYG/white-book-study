# CH10. Compiler - Syntax Analysis

컴파일은 크게 두 단계로 나뉜다.

- Syntax Analysis (구문 분석)
- Code Generation (코드 생성)

이번 장(10장)에서는 Syntax Analysis (구문 분석)을 다룬다. 구문 분석은 크게 두 가지 전략이 있다. 첫 번째로는 top-down (하향식), 두 번째는 bottom-up (상향식).

> **Warning**
>
> bottom-up 방식이 더 진보된 알고리즘인데, 더 정교한 이론을 알아야 하기 때문에 여기서는 top-down 방식을 설명하고 있다.
>
> 그리고 formal language theory (형식 언어 이론) 설명은 거의 대부분 생략되었다.
>
> 구문 분석기는 독립적인 프로그램은 아니며, 밑바닥부터 구현하는 경우는 드물다. 보통 토큰화 모듈이나 구문 분석기를 만들 때, Lex (어휘 분석 도구) 와 Yacc 과 같은 컴파일러 생성기 도구들을 이용한다. 이 도구들은 Context Free Grammer (CFG, 문맥 자유 문법)를 입력하면, 그 문법으로 작성된 프로그램을 토큰화하고 분석하는 문법 분석 코드를 출력한다. 그리고 컴파일 조건에 맞춰 생성 코드를 수정할 수 있다.
