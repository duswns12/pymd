
# **입출력**
    
```python
print("Hello World!")
input("input")
```
# **변수**
    
  * 파이썬에서는 변수를 선언할떄 타입을 지정하지 않는다.
```python
text = "TEXT"
num = 12345
```
    
# **자료형**
  ## **str**
  * string의 약자로, 문자열을 의미함
    
    ```python
    a = "ABC"
    ```
    
    ## **int**
    * integer의 약자로, 정수. 즉 숫자를 의미함
    ```python
    num = 123
    ```

    ## **list**
    * 말 그대로 리스트이다. 이후에 객체 수정이 가능함.
     
    ```python
    li = ["a" , "b"]
    print(li) #['a' , 'b']

    print(li[0]) #a

    li[0] = "A"  #리스트의 첫번째값을 A로 변경
    print(li) #['A' , 'b']

    li.insert(2 , "c") #세번째 자리에 c삽입
    print(li) #['A', 'b', 'c']
    ```

    ## **tuple**
    * 리스트와 비슷하게 여러가지를 담을 수 있으나, 수정이 불가능함.
     
    ```python
    tu  = ("a" , "b")
    print(tu) #('a', 'b')

    print(tu[0]) #a

    tu[0] = "A"
    print(tu) #결과값 : 에러
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
    a = 1
    a == 1 #True
    a == 2 #False
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
      ```
     ### 타입 확인
     * 자료형 타입을 확인할수있다.
     * 괄호에는 확인할 변수명이 들어간다.
    ```python
    type()
    ```
