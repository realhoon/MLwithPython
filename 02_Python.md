# 1. 파이썬 설치 및 jupyter notebook 실행

* 아나콘다 배포판 : <https://www.anaconda.com/download>
* 파이썬 버전 확인    
```> python --version```
* 터미널 창에서 jupyter notebook 실행    
```> jupyter notebook```
* ```jupyter notebook```에서 ```New``` 버튼 실행 후 ```Python3``` 항목 실행

</br>

# 2. 파이썬 데이터 타입(Data Type)

</br>

## 2.1 리스트(list)
* 리스트 데이터와 인덱스
<img width="750" alt="리스트인덱스" src="https://github.com/realhoon/MLwithPython/assets/86945081/587ccbac-2536-46e9-bdad-b9093db9ba38">
</br>

출처 : https://favtutor.com/blogs/get-list-index-python

</br>

* list data 참조

```
a = [10, 20, 30, 40, 50]

print('a[0] = ', a[0], ', a[2] = ', a[2], ', a[4] = ', a[4])
print('a[-1] = ', a[-1], ', a[-2] = ', a[-2], ', a[-5] = ', a[-5])

```

&nbsp;&nbsp;&nbsp;&nbsp;a[0] =  10 , a[2] =  30 , a[4] =  50   
&nbsp;&nbsp;&nbsp;&nbsp;a[-1] =  50 , a[-2] =  40 , a[-5] =  10

</br>

* list append method

```
b = [ ]
b.append(100), b.append(200), b.append(300)

print('b = ', b)
```

&nbsp;&nbsp;&nbsp;&nbsp;b =  [100, 200, 300]    

이 방법은 머신러닝에서 정확도를 계산하거나 손실된 함수 값을 임시로 저장할 때 많이 사용한다.

</br>

* list slice

```
c = [10, 20, 30, 40, 50]

print('c[0:2] = ', c[0:2], ', c[1:] = ', c[1:])
print('c[:3] = ', c[:3], ', c[:-2] = ', c[:-2])
print('c[:] = ', c[:])
```

&nbsp;&nbsp;&nbsp;&nbsp;c[0:2] =  [10, 20] , c[1:] =  [20, 30, 40, 50]    
&nbsp;&nbsp;&nbsp;&nbsp;c[:3] =  [10, 20, 30] , c[:-2] =  [10, 20, 30]   
&nbsp;&nbsp;&nbsp;&nbsp;c[:] =  [10, 20, 30, 40, 50]   

파이썬의 슬라이스는 콜론(:)을 중심으로 '왼쪽 인덱스'부터 '오른쪽 인덱스-1' 만큼의 원소 값을 가져온다.

</br>

## 2.2 튜플(tuple)

* tuple index, slice

```
a = (10, 20, 30, 40, 50)

print('a[0] = ', a[0], ', a[-2] = ', a[-2])
print('a[0:2] = ', a[0:2], ', a[1:] = ', a[1:] ',a[:] = ', a[:])
```

&nbsp;&nbsp;&nbsp;&nbsp;a[0] =  10 , a[-2] =  40    
&nbsp;&nbsp;&nbsp;&nbsp;a[0:2] =  (10, 20) , a[1:] =  (20, 30, 40, 50) ,a[:] =  (10, 20, 30, 40, 50)   

튜플은 소괄호로 묶어서 생성하고, 초기 데이터를 변경할 수 없는 읽기 전용 데이터이다.

* tuple error

```
a[0] = 100
```

&nbsp;&nbsp;&nbsp;&nbsp;---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-5-b6d7a4db9a51> in <cell line: 1>()
----> 1 a[0] = 100

TypeError: 'tuple' object does not support item assignment   

</br>

## 2.3 딕셔너리(dictionary)

* dictionary data

```
score = { 'KIM' : 90, 'LEE' : 85, 'JUN' : 95}

print(score)
print('score[KIM] = ', score['KIM'])
print(type(score))

score['HAN'] = 100
print(score)

print(score.keys())
print(score.values())
print(score.items())
```

&nbsp;&nbsp;&nbsp;&nbsp;{'KIM': 90, 'LEE': 85, 'JUN': 95}   
&nbsp;&nbsp;&nbsp;&nbsp;score[KIM] =  90   
&nbsp;&nbsp;&nbsp;&nbsp;<class 'dict'>   
&nbsp;&nbsp;&nbsp;&nbsp;{'KIM': 90, 'LEE': 85, 'JUN': 95, 'HAN': 100}   
&nbsp;&nbsp;&nbsp;&nbsp;dict_keys(['KIM', 'LEE', 'JUN', 'HAN'])   
&nbsp;&nbsp;&nbsp;&nbsp;dict_values([90, 85, 95, 100])   
&nbsp;&nbsp;&nbsp;&nbsp;dict_items([('KIM', 90), ('LEE', 85), ('JUN', 95), ('HAN', 100)])   

</br>

## 2.4 type(), len() 함수

* type(), len()

```
a = [10, 20, 30, 40, 50]
b = (10, 20, 30, 40, 50)
c = {'KIM':90, 'LEE':80}
d = [[100, 200], [300, 400], [500, 600]]

print(type(a), type(b), type(c), type(d))
print(len(a), len(b), len(c), len(d))
```

&nbsp;&nbsp;&nbsp;&nbsp;<class 'list'> <class 'tuple'> <class 'dict'> <class 'list'>   
&nbsp;&nbsp;&nbsp;&nbsp;5 5 2 3   

우선 머신러닝에는 학습 데이터가 필요하다. 학습 데이터는 다양한 소스에서 수집되고, 이러한 데이터들의 타입은 각양각색이므로 머신러닝 학습에 적합한 ```데이터 타입 Data Type```으로 변환해야 한다. 즉, 다양한 소스에서 수집된 ```데이터 타입```이 무엇인지 먼저 알아낸 후 머신러닝에 적합한 데이터로의 변환 과정이 반드시 필요하다. 이때 수집된 다양한 데이터의 타입을 ```type()```함수를 통해 알 수 있다.

</br>

```len()```함수는 변수에 포함되어 있는 원소의 개수를 출력해준다.

</br>

# 3. 파이썬 조건문 if

* if : if와 조건식만 사용

```
a = 1

if a > 0 :
  print("a ==", a)
  print("positive number")

elif a == 0 :
  print("a ==", a)
  print("zero")

else :
  print("a ==", a)
  print("negative number")
```

&nbsp;&nbsp;&nbsp;&nbsp; a == 1   
&nbsp;&nbsp;&nbsp;&nbsp; positive number

</br>

* if : if와 in 키워드 함께 사용

```
list_data = [10, 20, 30, 40, 50]
dict_data = {'key1':1, 'key2':2}

if 45 in list_data :
  print("45 is in list_data")

else :
  print("45 is not in list_data")

if 'key1' in dict_data :
  print("key1 is in dict_data")

else :
  print("key1 is not in dict_data")
```

&nbsp;&nbsp;&nbsp;&nbsp; 45 is not in list_data   
&nbsp;&nbsp;&nbsp;&nbsp; key1 is in dict_data   

코딩 블록을 표시할 대, 파이썬은 ```들여쓰기 Indentation```을 사용하며, ```동일한 블록 Block의 들여쓰기```는 모두 ```동일한 수의 공백```을 사용한다.

</br>

# 4. 파이썬 for 반복문

* 반복문 for : in range()

```
for data in range(10) :
  print(data, " ", end='')

for data in range(0, 10) :
  print(data, " ", end='')

for data in range(0, 10, 2) :
  print(data, " ", end='')
```

&nbsp;&nbsp;&nbsp;&nbsp; 0  1  2  3  4  5  6  7  8  9     
&nbsp;&nbsp;&nbsp;&nbsp; 0  1  2  3  4  5  6  7  8  9     
&nbsp;&nbsp;&nbsp;&nbsp; 0  2  4  6  8       

```end=''```의 의미는 print문을 실행한 후 다음 행으로 넘어가지 말고 같은 행에서 결과를 출력하라는 의미이다.

</br>

* 반복문 for : in + list/dictionary 

```
list_data = [10, 20, 30, 40, 50]

for data in list_data :
  print(data, " ", end='')

dict_data = {'key1' : 1, 'key2' : 2}

for data in dict_data :
  print(data, " ", end='')

for key, value in dict_data.items() :
  print(key, " ", value)
```

&nbsp;&nbsp;&nbsp;&nbsp; 10  20  30  40  50   
&nbsp;&nbsp;&nbsp;&nbsp; key1  key2   
&nbsp;&nbsp;&nbsp;&nbsp; key1   1   
&nbsp;&nbsp;&nbsp;&nbsp; key2   2   

</br>

* 반복문 while

```
data = 5

while data >= 0 :
  print("data ==", data)
  data -= 1
```

&nbsp;&nbsp;&nbsp;&nbsp; data == 5    
&nbsp;&nbsp;&nbsp;&nbsp; data == 4    
&nbsp;&nbsp;&nbsp;&nbsp; data == 3    
&nbsp;&nbsp;&nbsp;&nbsp; data == 2    
&nbsp;&nbsp;&nbsp;&nbsp; data == 1    
&nbsp;&nbsp;&nbsp;&nbsp; data == 0    

```
data = 5

while data >= 0 :
  print("data ==", data)
  data -= 1

  if data == 2:
    print("break here")
    break

  else :
    print("continue here")
    continue
```
&nbsp;&nbsp;&nbsp;&nbsp; data == 5    
&nbsp;&nbsp;&nbsp;&nbsp; continue here    
&nbsp;&nbsp;&nbsp;&nbsp; data == 4    
&nbsp;&nbsp;&nbsp;&nbsp; continue here    
&nbsp;&nbsp;&nbsp;&nbsp; data == 3    
&nbsp;&nbsp;&nbsp;&nbsp; break here    

</br>

# 5. List Comprehension

List Comprehension은 리스트 변수 내부에 for 구문을 이용해서 데이터를 만드는 방법을 말한다. 이러한 List Comprehension은 머신러닝에서 데이터를 조작하고 원하는 형식으로 만들어 내기 위해 자주 사용하는 기법이다.

* 파이썬 List Comprehension 사용법

```
list_data = [ x ** 2 for x in range(5) ]
print(list_data)
```

&nbsp;&nbsp;&nbsp;&nbsp; [0, 1, 4, 9, 16]

```
raw_data = [ [1, 10], [2, 15], [3, 30], [4, 55] ]

all_data = [ x for x in raw_data ]
x_data = [ x[0] for x in raw_data ]
y_data = [ x[1] for x in raw_data ]

print("all_data ==", all_data)
print("x_data ==", x_data)
print("y_data ==", y_data) 
```

&nbsp;&nbsp;&nbsp;&nbsp; all_data =  [[1, 10], [2, 15], [3, 30], [4, 55]]    
&nbsp;&nbsp;&nbsp;&nbsp; x_data =  [1, 2, 3, 4]    
&nbsp;&nbsp;&nbsp;&nbsp; y_data =  [10, 15, 30, 55]    

</br>

* 짝수 출력

```
even_number = [x for x in range(10) if x % 2 == 0]

print(even_number)
```

&nbsp;&nbsp;&nbsp;&nbsp; [0, 2, 4, 6, 8]

</br>

# 6. 파이썬 함수(Function)

</br>

## 6.1 함수 정의와 리턴 값

특정 기능을 수행하는 명령어들을 하나로 묶어 함수로 정의할 수 있으며, 파이썬 함수는 다음과 같이 def 키워드로 정의할 수 있다.

* 파이썬 함수 정의와 사용법
```
def sum(x, y) :

  s = x + y
  return s

result = sum(10, 20)
print(result)
```
&nbsp;&nbsp;&nbsp;&nbsp; 30    

</br>

파이썬에서는 함수의 리턴 return 값으로 1개 이상의 변수를 리턴할 수 있다. 각각의 리턴 값을 콤마(,)로 분리하거나 튜플 형식으로 소괄호를 씌워서 리턴할 수 있다.

* 1개 이상의 값을 리턴하는 파이썬 함수 정의와 사용법

```
def multi_ret_func(x) :

  return x+1, x+2 , x+3

x = 100
y = y1, y2, y3 = multi_ret_func(x)

print(y)

```

&nbsp;&nbsp;&nbsp;&nbsp;(101, 102, 103)

</br>

## 6.2 디폴트 파라미터(Default Parameter)

디폴트 파라미터는 기본 값을 함수의 입력 파라미터로 지정하는 것을 말한다.

* 디폴트(Default) 파라미터 정의와 사용법

```
def print_name(name, count=2) :

  for i in range(count) :
    print('name ==', name)

print_name("DAVE")
print()
print()
print_name("DAVE", 7)
```
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    

</br>

&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    
&nbsp;&nbsp;&nbsp;&nbsp; name == DAVE    

</br>

## 6.3 mutable, immutable 파라미티(Parameter)

* mutable : 입력 파라미터로 들어간 변수의 원본 값을 함수 내에서 바꿀 수 있는 것. ```list, dictionary, numpy```
* immutable : 입력 파라미터로 들어간 변수의 원본 값이 함수 내에서 바뀌지 않는 데이터 타입. ```숫자, 문자, 튜플```
</br>
* mutable, immutable type

```
def mutable_immutable_func(int_x, input_list) :

  int_x += 1
  input_list.append(100)

x = 1
test_list= [1, 2, 3]

mutable_immutable_func(x, test_list)

print('x == ', x, ', test_list == ', test_list)
```

&nbsp;&nbsp;&nbsp;&nbsp; x ==  1 , test_list ==  [1, 2, 3, 100]    
</br>

파이썬에서 함수를 작성하고 ```입력 파라미터 Parameter```로 ```mutable 데이터 타입```을 받는 경우에는 함수 내에서 원본 값이 변경되지 않게 보관하고, 함수 내에서 다양한 작업을 수행한 후에 보관되어 있는 값을 다시 복원시키는 과정이 반드시 필요하다.

</br>

## 6.4 람다(lambda)함수

```람다 함수```는 함수를 만들 때 def를 사용하지 않고 한 줄 형태로 함수를 작성하는 것. 람다 함수는 특히 머신러닝에서 ```수치미분```과 ```활성화 함수``` 등을 일반적인 수학에서의 함수 표기법 f(x), f(x, y)로 나타낼 때 사용한다.

* 람다의 정의와 사용법

```
f = lambda x : x + 100

for i in range(3) :
  print(f(i))

```

&nbsp;&nbsp;&nbsp;&nbsp; 100    
&nbsp;&nbsp;&nbsp;&nbsp; 101    
&nbsp;&nbsp;&nbsp;&nbsp; 102    

람다는 ```lambda를 대표하는 함수 이름```과 ```입력 변수```, 그리고 ```이들을 대체할 수 있는 표현식```으로 정의한다. 대체한다는 의미는 C언어에서 사용되는 #define과 같은 개념이다. #define f(x) (x+100)

```
def print_hello() :

  print("hello python")

def test_lambda(s, t) :

  print("input1 ==", s, ", input2 ==", t)

s = 100
t = 200

fx = lambda x, y : test_lambda(s, t)
fy = lambda x, y : print_hello()

fx(500, 1000)
fy(300, 600)

```

&nbsp;&nbsp;&nbsp;&nbsp; input1 == 100 , input2 == 200    
&nbsp;&nbsp;&nbsp;&nbsp; hello python    

</br>

# 7. 파이썬 클래스(class)

</br>

 파이썬에서 ```클래스 class```는 ```클래스 class 키워드```를 사용하며, ```함수를 만들 때 사용한 def```를 통해 ```클래스 class 메서드 method```를 정의할 수 있다.    
 먼저 ```__init__ 메서드```는 파이썬 클래스가 반드시 가져야하는 메서드로서, ```생성자 Constructor``` 역할을 수행하며, ```객체 Object```가 만들어질 때 자동으로 한번만 호출된다.    
</br>
  또한 파이썬에서는 ```메서드의 첫 번째 입력 파라미터```로써, ```자기 자신을 나타내는 self```를 반드시 써주어야 한다. self는 C++, java 언어의 this 처럼 자기 자신을 가리킨다.

* 파이썬 클래스 정의 및 기본 예제

```
class Person :

  def __init__(self, name) :
    self.name = name
    print(self.name + " is initialized")

  def work(self, company) :
    print(self.name + " is working in " + company)

  def sleep(self) :
    print(self.name + " is sleeping")


obj = Person("PARK")
print(obj)

print()

obj.work("ABCDEF")
obj.sleep()

print()

print("current person object is ", obj.name)
```

&nbsp;&nbsp;&nbsp;&nbsp; PARK is initialized    
<__main__.Person object at 0x7ae972e5b2e0>    
&nbsp;&nbsp;&nbsp;&nbsp; PARK is working in ABCDEF    
&nbsp;&nbsp;&nbsp;&nbsp; PARK is sleeping    
&nbsp;&nbsp;&nbsp;&nbsp; current person object is  PARK   

</br>

 ```객체 obj```를 생성하면 Person 클래스 생성자인 ```__init__``` 내에서 ```self.name = name```이 실행된다. 여기서 ```self.name```은 클래스의 ```멤버 변수```를 가리키며, C++이나 java와 달리 파이썬에서는 클래스 내에서 멤버 변수 선언을 별도로 하지 않아도 바로 사용할 수 있다.    
 ```name```은 Person 클래스가 가지고 있는 ```인스턴스 instance 변수```인데, 보다시피 ```객체 obj```를 이용하여 바로 접근해서 값을 가져올 수 있다. 이처럼 파이썬에서는 ```메서드```와 ```멤버 member 변수``` 모두가 기본적으로 ```public```으로 선언되기 때문에 외부에서 생성한 객체를 통하여 바로 접근해서 사용할 수 있다.

</br>

* 출처 : <https://www.youtube.com/watch?v=5Xy5Ju7hYo4&list=PLS8gIc2q83OjStGjdTF2LZtc0vefCAbnX&index=5>

```
class Person :

  count = 0

  def __init__(self, name) :
    self.name = name
    Person.count += 1
    print(self.name + "is initialized")

  def work(self, company) :
    print(self.name + "is working in" + company)

  def sleep(self) :
    print(self.name + "is sleeping")

  @classmethod
  def getCount(cls) :
    return cls.count

obj1 = Person("PARK")
obj2 = Person("KIM")

obj1.work("ABCDEF")

obj2.sleep()

print("current person object is", obj1.name, ", ", obj2.name)

print("Person count ==", Person.getCount())

print(Person.count)
```
&nbsp;&nbsp;&nbsp;&nbsp; PARK is initialized        
&nbsp;&nbsp;&nbsp;&nbsp; KIM is initialized    
&nbsp;&nbsp;&nbsp;&nbsp; PARK is working in ABCDEF    
&nbsp;&nbsp;&nbsp;&nbsp; KIM is sleeping    
&nbsp;&nbsp;&nbsp;&nbsp; current person object is PARK, KIM    
&nbsp;&nbsp;&nbsp;&nbsp; Person count == 2    
&nbsp;&nbsp;&nbsp;&nbsp; 2    

```
class PrivateMemberTest :

  def __init__(self, name1, name2) :
      self.name1 = name1
      self.__name2 = name2

      print("initialized with " + name1 + " ," + name2)

  def getNames(self) :
      self.__printNames()
      return self.name1, self.__name2

  def __printNames(self) :
      print(self.name1, self.__name2)

obj = PrivateMemberTest("PARK", "KIM")

print(obj.name1)
print(obj.getNames())
print(obj.__printNames())  # error  
print(obj.__name2)         # error
```

&nbsp;&nbsp;&nbsp;&nbsp; initialized with PARK ,KIM    
&nbsp;&nbsp;&nbsp;&nbsp; PARK    
&nbsp;&nbsp;&nbsp;&nbsp; PARK KIM    
&nbsp;&nbsp;&nbsp;&nbsp; ('PARK', 'KIM')    
&nbsp;&nbsp;&nbsp;&nbsp; ---------------------------------------------------------------------------    
&nbsp;&nbsp;&nbsp;&nbsp; AttributeError                            Traceback (most recent call last)
&nbsp;&nbsp;&nbsp;&nbsp; <ipython-input-3-dbc15b89f7fb> in <cell line: 23>()
&nbsp;&nbsp;&nbsp;&nbsp;     21 # print(obj.name2)
&nbsp;&nbsp;&nbsp;&nbsp;     22 print(obj.getNames())
&nbsp;&nbsp;&nbsp;&nbsp;---> 23 print(obj.__printNames())
&nbsp;&nbsp;&nbsp;&nbsp;     24 print(obj.__name2)

AttributeError: 'PrivateMemberTest' object has no attribute '__printNames'    

```
def print_name(name) :
  print("[def] ", name)

class SameTest :

  def __init__(self) :

    pass

  def print_name(self, name) :
    print("[SameTest] ", name)

  def call_test(self) :

    print_name("KIM")

    self.print_name("KIM")

obj = SameTest()

print_name("LEE")

obj.print_name("LEE")

obj.call_test()
```

&nbsp;&nbsp;&nbsp;&nbsp; [def]  LEE    
&nbsp;&nbsp;&nbsp;&nbsp; [SameTest]  LEE    
&nbsp;&nbsp;&nbsp;&nbsp; [def]  KIM    
&nbsp;&nbsp;&nbsp;&nbsp; [SameTest]  KIM    

</br>

# 7. 정리 및 기타


 파이썬 리스트 변수에는 음수 인덱스와 슬라이스 기능이 있다는 것을 반드시 기억하자. 또한 학습 데이터 생성을 위해 자주 사용되는 List Comprehension을 잘 숙지해 놓으면 차후에 코드를 간결하게 구현할 수 있다.

</br>

그 밖의 개념

* 예외 Exception

```
def calc(list_data) :

  sum = 0

  try :
    sum = list_data[0] + list_data[1] + list_data[2]

    if sum < 0 :
      raise Exception("Sum is minus")

  except IndexError as err :
    print(str(err))

  except Exception as err :
    print(str(err))

  finally :
    print(sum)


calc([1, 2])

calc([1, 2, -100])
```

&nbsp;&nbsp;&nbsp;&nbsp; list index out of range     
&nbsp;&nbsp;&nbsp;&nbsp; 0    
&nbsp;&nbsp;&nbsp;&nbsp; Sum is minus    
&nbsp;&nbsp;&nbsp;&nbsp; -97    

</br>

* 파일 읽기 및 쓰기

```
f = open("./file_test", 'w')

f.write("Hello, Python !!!")

f.close()
```
```
with open("./file_test", 'w') as f :
  f.write("Hellp, Python !!!")
```
