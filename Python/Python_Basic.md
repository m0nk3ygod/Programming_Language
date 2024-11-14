# Python

# - Python 설치

[https://www.python.org/downloads/](https://www.python.org/downloads/)

## - VSCode 설치

[https://code.visualstudio.com/download](https://code.visualstudio.com/download)

python 맛보기

# Hello World!

```python
print("hello world!")
```

---

## 0. 기본 문법

### 들여쓰기

- 파이썬은 다른 언어들과 달리 들여쓰기를 통해 코드를 묶음
- 코드를 여럿 묶어야할 때는 콜론( : ) 을 사용
- 다른 언어와 달리 세미 콜론( ; )을 사용하지 않음

```
# C Example

int add(a, b) {
	return a + b;
}

result = add(a, b);
printf(result);
```

```python
# Python example

def add(a, b):
	return a + b
	
result = add(a, b)
print(result)

```

### 주석처리

- 코드 실행이나 결과에 전혀 영향이 없음
- 코드의 기능 설명이나 메모하고 싶은 내용을 입력
- # 형태로 사용

```python
def add(a, b): # 함수 add 선언
	return a + b # 함수 add 내용

result = add(1, 2) # 함수 실행 후 결과를 result에 담음
print(result) # 함수 결과 출력

```

---

## 1. 데이터 타입

### Bool

- 논리형식으로 다루는 데이터
- “참(True)”, “거짓(False)”
- bool 함수를 사용하여 True와 False를 리턴
- 0 or None 인 경우 False, data가 존재할 경우 True

```python
# True

bool(1)  # result : True
bool(-1) # result : True
bool(['test']) # result : True

# False

bool(0) # result : False
bool(None) # result : False
bool([]) # result : False

```

- 논리 연산자

a = True, b = False 일때

| 코드 | 기호 | 의미 | 예시 |
| --- | --- | --- | --- |
| and | & | 논리곱 | a and b = False |
| or | | | 논리합 | a or b = True |
| not | ! | 부정 | not(a and b) = True |

### 문자열

1. 싱글 쿼터 ( ‘ ), 더블 쿼터 ( “ )
    - 문자열을 입력할 때는 싱글 쿼터와 더블 쿼터를 사용
    - 두 가지 쿼터를 번갈아 사용하거나, 백 슬래시 ( \ )를 사용하여 싱글 쿼터와 더블 쿼터를 문자열의 일부로 사용 가능
    
    ```python
    print('I am Monkey') # I am Monkey
    print("I am GOD") # I am GOD
    
    print("I'm Monkey") # I'm Monkey
    
    print('Monkey says "I am GOD"') # Monkey says "I am GOD"
    
    print("I\'m GOD") # I'm GOD
    ```
    
2. 이스케이프 시퀀스 \n, row Strings r’ ‘
    - \n 을 사용하여 줄 바꿈을 실행 (new line)
    
    ```python
    print('1st\n2nd')
    
    # result :
    1st
    2nd
    
    ```
    
    - 문자열 앞에 ‘r’을 삽입하여 raw strings으로 사용
    
    ```python
    print(r'1st\n2nd')
    
    # result :
    1st\n2nd
    
    ```
    
3. “””…””” 또는 ‘’’…’’’
    - 다수의 새로운 줄을 삽입할 때 사용
    - 이 문구 내에서 엔터를 삽입하면 자동으로 새로운 줄로 인식하여 출력
    - \ 를 삽입하면 엔터를 무시
    
    ```python
    print("""\
    Usage: things [OPTIONS]
    	-h                    Display this usage message
    	-H   hostname     .   Hostname to connect to
    """)
    
    # result :
    Usage: things [OPTIONS]
    	-h                    Display this usage message
    	-H   hostname     .   Hostname to connect to
    ```
    
4. 문자열 연산
    - + 연산을 사용하여 문자열을 합침
    
    ```python
    'Monkey' + 'GOD'
    
    # MonkeyGOD
    ```
    
    - * 연산을 사용하여 문자를 여러번 출력
    
    ```python
    'GOD' * 3
    
    # GODGODGOD
    ```
    

---

## 2. 출력과 입력

### 출력 print()

print() 함수를 사용하여 다양한 데이터를 출력할 수 있음

```python
a = 1

print(a) # 변수 출력
print('string') # 문자열 출력
print(10) # 숫자 출력
print(True) # bool 형 출력
```

- 변수 출력

```python
a = 10
b = 20

print(a) # 10
print(a, b) # 10 20
print("{} {}".format(a, b)) # 10 20
print("%d %d"%(a, b)) # 10 20
```

### 입력 input()

input() 함수를 사용하여 사용자의 입력을 받아올 수 있음

```python
userInput = input("what number?")
print("your number is", userInput)

# what number? (유저의 입력을 기다림. 입력 후 엔터)

# your number is [ 유저 입력값 ]
```

### 간단한 계산기

```python
print("simple add calc")

a = int(input("a :")) # 입력 받은 값을 int()로 묶어주면 정수형태로 변환이 된다.
b = int(input("b :")) # 입력 받은 값을 int()로 묶어주면 정수형태로 변환이 된다.

print("{} + {} = {}".format(a, b, a+b))
```

<aside>
**💡 int() 를 사용해서 정수형태로 바꾸는 이유는?**

input() 함수는 사용자에게서 입력 받은 값을 문자열로 처리를 한다. 
`print("{} + {} = {}".format(a, b, a+b))` 
그렇기에 여기 코드에서 사용된 a+b 는 우리가 생각한대로 숫자가 더해지는게 아니라 문자열이 합쳐지는 결과가 나오게 된다.
(a : 1, b : 2 라고 하면 12가 나오게 된다.)

입력받은 값을 숫자 형태로 사용하기 위해서 바꾸는 작업을 해주어야 되기에 int()를 사용하는 것이다.

</aside>
