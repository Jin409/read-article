### Django_4.0_릴리스와_주요_변경사항.md
https://www.44bits.io/ko/post/django-4-0-release-note-summary

1. 타임존 => zoneinfo 로
- 파이썬 기본 라이브러리인 zoneinfo 가 타임존
- pytz 는 완전히 삭제할 예정

2. 함수형 고유키 제약
- UniqueContraint() 사용 가능
```Python
class Shop(models.Model):
    name = models.CharField(max_length=255)
    class Meta:
        constraints = [
            UniqueConstraint(Lower('name'),
            name='unique_name')
        ]
```
- 예를 들어, OnlineShop 을 저장했다면 Onelineshop 을 저장할 수 없음. 

3. 템플릿 기반의 폼 렌더링 가능
```Python
from shop.forms import CartForm
def cart(request):
    CartFormSet = formset_factory(CartForm)
    if request.method == 'POST':
        formset = CartFormSet(request.POST)
    else:
        formset = CartFormSet()
    return render(request, 'cart.html', {'formset': formset})
```
```html
<table>
        {% for form in formset %}
        {{ form }}
        {% endfor %}
    </table>
```
- 이제는 view 에서 formset.template_name 속성을 선언한다면 html 을 아래와 같이 수정 가능.
```html
<table>
        {{ formset }}
    </table> 
```
4. 관리자 화면 
- admin/base.html 파일에 Header 블럭 추가됨
- 내비게이션 바에 필터 추가

5. django.contrib.postgres
- 서비스 이름으로 연결할 수 있음 => 이해 못함

6. AddConstraintNotValid
- 새로운 데이터에만 제약 조건 적용 가능

7. ValidateConstraint
- 기존 데이터가 제약 조건을 위반하는지 확인 가능

8. ArraySubquery 표현식 추가
- Queryset.value()의 리턴 값을 배열처럼 접근 가능

9. 모델
- Round() 데이터베이스 함수에 정밀도 지정할 수 있는 precision 전달인자 추가
