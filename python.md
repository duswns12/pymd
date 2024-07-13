
# **출력**
    
```python
print("Hello World!") #Hello World! 출력
```

# **입력**
```python
inp = input("값을 입력하세요: ") #값을 입력받는다.
print(inp)  #입력받은 값을 출력한다.
```

# **변수**
* 변수는 저장 공간이다.  
* 파이썬에서는 변수를 선언할떄 타입을 지정하지 않는다.
```python
text = "TEXT"
num = 12345
```
    
# **자료형**
## **str**
* string의 약자로, 문자열을 의미함
* 문자열은 "큰따옴표"나 '작은따옴표'로 감싼다.
    
```python
a = "ABC"
```
    
## **int**
* integer의 약자로, 정수. 즉 숫자를 의미함
```python
num = 123
```

## **list**
* 말 그대로 리스트이다.
* 특징:
    * 이후에 객체의 수정이 가능함.
    * 대괄호를 사용해서 리스트의 특정 위치에 있는 값만 가져올수있음
    * 특정 요소만 찾는것도 가능함.

```python
li = ["a" , "b"]
print(li) #["a" , "b"]

print(li[0]) #a

li[0] = "A"  #리스트의 첫번째값을 A로 변경
print(li) #['A' , 'b']

li.insert(2 , "c") #세번째 자리에 c삽입
print(li) #['A', 'b', 'c']

print("a" in li) #True
print(1 in li) #False
```

## **tuple**
* 리스트와 비슷하게 여러가지를 담을 수 있음.
* 특징:
    * 리스트와는 다르게 수정이 불가함.
    * 대괄호를 사용해서 리스트의 특정 위치에 있는 값만 가져올수있음
    * 특정 요소만 찾기 가능함.
     
```python
tu  = ("a" , "b")
print(tu) #("a", "b")

print(tu[0]) #a

tu[0] = "A"
print(tu) #결과값 : 에러

print("a" in tu) #True
print(1 in tu) #False
```

## **set**
* 리스트, 튜플처럼 여러가지를 담을 수 있다.
* 특징:
    * 대괄호를 사용해서 특정 위치에 있는 값만 가져오는게 불가능함.
    * 하지만 요소 찾기는 가능함.
    * 순서가 없으며, 중복이 불가능함.

```python
se = {"a","b","b"}
print(se) #{"a","b"} -> 중복은 제거됨

print("a" in se) #True
print("c" in se) #False
```    

## **dictionary**
* 사전이라는 뜻으로, 키:값 형태로 이루어져있다.
* 값에 접근하려면 키가 있어야한다.
     
```python
dic = {"key":"value",}
print(dic.get("key")) #value

print(dic.keys()) #모든 키 반환
print(dic.values()) #모든 값 반환
print(dic.items()) #모든 키:값 반환

dic["key"] = "value0" #key:value를 key:value0로 변경
dic["key2"] = "value2" #key2:value2 생성
```

 ## **bool**
* boolean의 약자로, 참과 거짓으로 이루어진 자료형이다.
* 참고로 파이썬에서는 True, False로 앞글자가 대문자다.
     
```python
print(1 == 1) #True
print(3 == 5) #False
```

## **기타**
### 타입 변환
* 자료형의 타입을 변환한다.
* 괄호에는 바꿀 변수명이 들어간다.
```python
str()
int()
float()
list()
tuple()
set()

a = 1
str_a = str(a)
print(type(str_a)) # <class 'str'>
```
### 타입 확인
* 자료형 타입을 확인할수있다.
* 괄호에는 확인할 변수명이 들어간다.
```python
type()

a = "abc"
print(type(a)) # <class 'str'>
```

# **함수**
* 함수는 코드의 묶음이다.
* 왜씀?
    * 코드의 재사용성과 가독성이 좋아짐
* 어떻게 씀?
    ```python
    def 변수명():
        코드    
    ```    
* 참고로 파이썬에선 들여쓰기로 코드 블록을 나눔.(들여쓰기가 중요함)
```python
# 함수 미사용
print("A의 나이는 21살 입니다.")
print("B의 나이는 22살 입니다.")
print("C의 나이는 23살 입니다.")
print("D의 나이는 24살 입니다.")
print("E의 나이는 25살 입니다.")
print("F의 나이는 26살 입니다.")

# 함수 사용
def info(name,age):
    print(f"{name}의 나이는 {age}살 입니다.")

li = [("a",21),("b",22),("c",23),("d",24),("e",25),("f",26)]

for name,age in li:
    info(name,age)

# 결과는 같음
```

# **포매팅**
* 그게뭐임?
    * 데이터를 보기좋게 표현하는 과정.
* 왜함?
    * 가독성이 좋아짐. 코드뿐만 아니라 출력 결과도 좋아짐.
```python
name = "A"

print("제 이름은 %s입니다." % (name)) #포매팅 첫번째 방법
print("제 이름은 {}입니다.".format(name)) #포매팅 두번째 방법
print(f"제 이름은 {name}입니다.") #포매팅 세번째 방법
# 결과는 모두 같음

#숫자,날짜 포매팅

######################### 숫자
number = 1234.56789

# 소수점 두 자리까지 포매팅
print(f"{number:.2f}")  # 1234.57

# 천 단위 구분 기호 추가
print(f"{number:,.2f}")  # 1,234.57

######################### 날짜
from datetime import datetime

now = datetime.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))  # 예: 2024-07-14 12:34:56
```

# **연산자**
* 파이썬에서는 여러가지 연산자가 있고, 각각 특정한 역할을 수행함.

## **산술 연산자**
* '+' : 덧셈
* '-' : 뺄셈
* '*' : 곱셈
* '/' : 나눗셈
* '//' : 몫
* '%' : 나머지
* '**' : 지수(제곱)
```python
a = 10
b = 3

print(a + b)  # 13
print(a - b)  # 7
print(a * b)  # 30
print(a / b)  # 3.3333...
print(a // b)  # 3
print(a % b)  # 1
print(a ** b)  # 1000
```

## **비교 연산자**
* '==' : 같음
* '!=' : 같지 않음
* '>' : 큼
* '<' : 작음
* '>=' : 크거나 같음
* '<=' : 작거나 같음
```python
a = 10
b = 20

print(a == b)  # False
print(a != b)  # True
print(a > b)  # False
print(a < b)  # True
print(a >= b)  # False
print(a <= b)  # True
```
## **논리 연산자**
* 'and' : 두 조건이 모두 참일 때 참
* 'or' : 두 조건 중 하나라도 참이면 참
* 'not' : 조건이 거짓이면 참, 참이면 거짓
```python
x = True
y = False

print(x and y)  # False
print(x or y)  # True
print(not x)  # False
```

## **멤버십 연산자**
* 'in' : 시퀀스 내에 값이 있으면 참
* 'not in' : 시퀀스 내에 값이 없으면 참
```python
a = [1, 2, 3, 4, 5]
print(3 in a)  # True
print(6 in a)  # False
print(6 not in a)  # True
```
## **아이덴티티 연산자**
* 'is' : 두 객체가 동일한 객체이면 참
* 'is not' : 두 객체가 동일한 객체가 아니면 참
```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)  # True
print(a is c)  # False
print(a is not c)  # True
```

# **조건문**
* 말 그대로 조건문임
    * 만약 ~ 라면 ~해라
* 종류:
    * if : 기본적인 조건문, 만약 ~ 라면 ~ 해라
    * else : 마지막에 실행되는 조건문, 만약 (모든 조건이)아니라면 ~해라
    * elif : else if 의 약자이다, 만약 (위의 조건이)아니고 ~라면 ~해라
```python
score = 90
if score >= 90:         #if 조건:
    print("A학점입니다.")#  코드
elif score >= 80:       #elif 조건:
    print("B학점입니다.")#  코드
else:                   #else:
    print("C학점입니다.")#  코드
```

# **반복문**
* 블록을 반복함.
* 종류
    * for 반복문 : for 반복문은 반복 횟수가 정해져 있거나 시퀀스(리스트, 튜플 등)의 각 요소를 처리할 때 주로 사용됨.
    * while 반복문 : while 반복문은 특정 조건이 참(True)일 동안 반복을 계속하며, 반복을 멈추는 조건을 명시적으로 설정해야 함.
* 어떻게 씀?
    * for 변수 in 시퀀스(반복횟수):
        코드
    * while 조건:
        코드
* 추가 : 반복문 내에서 break 문을 사용하여 반복을 중단하거나, continue 문을 사용하여 반복의 다음 순회로 넘어갈 수 있음.
```python
for i in range(10):
    print(f"for 반복문,{i+1}번째")

# for 반복문,1번째
# for 반복문,2번째
# for 반복문,3번째
# for 반복문,4번째
# for 반복문,5번째
# for 반복문,6번째
# for 반복문,7번째
# for 반복문,8번째
# for 반복문,9번째
# for 반복문,10번째

n = 1
while n<=5:
    print(f"while 반복문,{n}번째")
    n+=1

# while 반복문,1번째
# while 반복문,2번째
# while 반복문,3번째
# while 반복문,4번째
# while 반복문,5번째

while True:  #이 코드는 블록을 코드 자체를 멈출때까지 반복한다.
    print("무한 루프")
```

# **pass**
* pass는 함수,조건문,반복문 등의 형태만 유지하고싶을때 사용한다.
* 왜씀?
    * 코드의 틀만 미리 잡아놓을 수 있음
```python
def func():
    pass

if 1==1:
    pass

for i in range():
    pass

while True:
    pass
```

# **return**
* return은 함수, 조건문 등에서 값을 반환해주는 역할을함.
* 왜씀?
    * 값을 반환해주기 위해서, 반환반은값을 다른 변수에 할당하거나 계산에 이용이 가능함.
* 특징 :
    * 문자열, 숫자 뿐만아니라 불리언 형태도 가능하다.
```python
def add(a, b):
    result = a + b
    return result

sum_result = add(3, 5)
print("합계는:", sum_result)  # 출력: 합계는: 8
#####################################################
def is_even(number):
    if number % 2 == 0:
        return True
    else:
        return False

print(is_even(7))   # 출력: False
print(is_even(10))  # 출력: True

```    
