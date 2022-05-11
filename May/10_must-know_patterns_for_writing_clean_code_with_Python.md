## 10 must-know patterns for writing clean code with Python 🐍
https://dev.to/alexomeyer/10-must-know-patterns-for-writing-clean-code-with-python-56bf

1. 클린코드는 highly focused 되어야한다.
    - 각 클래스, 함수, 모듈은 할 일을 제대로 해야 한다.
2. 클린코드는 읽기 쉬워야 한다.
3. 클린코드는 디버그하기 쉬워야 한다.
4. 클린코드는 유지되기 쉬워야 한다.
  - 다른 개발자에 의해 향상되기 쉬워야 한다.
5. 클린코드는 성능이 좋아야 한다.

**********

#### Naming Convention

1. 길고 설명이 잘 되어 있는 이름을 써라 => 코멘트를 덧붙일 이유가 없어진다
```Python
# au는 number of activer users
au = 105
# better
total_active_users = 105
```

2. 의도가 나타나도록 써라
```Python
c = ['UK','USA']
for x in c:

#better
cities = ['UK','USA']
for city in cities:
```

3. 애매한 줄임말을 지양해라
4. 일관된 규칙을 사용해라 (구조, 변수명, 함수명, 경로명에도)
```Python
#bad code
def fetch_clients(response, variable):
    # do something
    pass

def fetch_posts(res, var):
    # do something
    pass

# Recommended
def fetch_clients(response, variable):
    # do something
    pass

def fetch_posts(response, variable):
    # do something
    pass
```
5. 항상 에디터 내에서 코드베이스의 이슈를 추적해라
6. 매직넘버를 쓰지마라 ex) random.randint

#### Functions
1. 함수명 규칙이 일관되게 하라
2. 한 가지 일을 잘 해내게 하라
3. Boolean flags 를 쓰지 말아라

#### Classes
1. 불필요한 내용을 담지 말아라

#### 정형화되어 있는 코드를 유지하기 원한다면,
- 로직을 여러개의 파일이나 클래스로 나누고 모듈로 불러와라

- 결론 : 클린코드로 technical debt 를 줄여야 한다.
