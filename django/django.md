## 💻 DJANGO

---

#### 1️⃣ 장고는 파이썬 web framwork

◾ Static web page(정적 웹페이지) - html, css, js

> 클라이언트가 요청 시, 추가적인 처리 없이 준비된 파일을 전달 함
>
> 모든 상황에서 모든 사용자에게 동일한 정보를 표시

◾ Dynamic web page(동적 웹페이지) - python, java ...

> 클라이언트의 요청을 받으면, 추가적인 처리 과정 이후 응답을 보냄
>
> 방문자와 상호작용 하므로 페이지 내용은 그때 그때 다름

◾ framework 란?

> 클래스+라이브러리. 웹페이지를 개발하는 데에서 겪는 어려움을 줄이는 것이 주 목적

◾ framework architecture

- MVC 디자인 패턴 (Model-View-Controller)
- 장고에서는 MTV 패턴 이라고 함
  - Model : 데이터베이스의 기록을 관리
  - Template : 실제 내용을 보여주는 데 사용
  - View : HTTP 요청을 수신, 응답 반환. Model을 통해 요청을 충족시키는데 필요한 데이터에 접근. Template에게 응답의 서식 설정을 맡김
  - 기본적인 흐름
  - 이미지 넣기



#### 2️⃣ DJANGO 설치와 설정

1. 가상환경 만들기

   ```bash
   $ python -m venv 가상환경명(보통 venv)
   ```

2. 활성화 시키기

   ```bash
   $ source venv/scripts/activate
   ```

3. 확인 (가상환경이 잘 설치되었는지 꼭 확인하기)

   ```bash
   $ pip list	
   ```

4. 장고 설치

   ```bash
   $ pip install django==3.2(버전)
   ```

5. 확인 (manage.py 생성 되었는지)

   ```bash
   $ ls
   ```

6. requirements.txt 만들기. 가상환경 관리 위함

   ```bash
   $ pip freeze > requirements.txt
   ```

7. 프로젝트 만들기

   ```bash
   $ django-admin startproject 프로젝트명 경로(보통 현재경로 .)
   ```

8. 확인 -> 서버 가동-> 로켓 나오면 성공

   ```bash
   $ python manage.py runserver
   ```

9. 앱 만들기

   ```bash
   $ python manage.py startapp 앱이름(보통 복수형)
   ```

   > 앱은 만들고 나서 바로 프로젝트 settings.py/INSTALLED_APPS에 등록해야함.ㅠ
   > 실제 요청을 처리하고 페이지를 보여주는 등의 역할을 담당함.
   >
   > 일반적으로 하나의 역할 및 기능 단위로 작성함.

◾ 하나의 Project에는 여러가지 App이 존재할 수 있다. 



#### 3️⃣ 요청과 응답

1. <b>urls</b> : HTTP 요청을 알맞은 views로 전달. 

   ```python
   path('index/', views.index) 
   ```

   - '' 사이를 비워두면 기본 경로에 html 문서가 뜸

2. <b>views</b> : HTTP 요청을 수신해서 응답을 반환하는 함수 작성

   ```pyth
   def index(request):
       context = {
           키 : 값 ,
       }
       return render(request, 'index.html', context)
   ```

3. <b>templates</b> : 반드시 앱 폴더 <u>내부</u>에 templates 폴더명을 가지고, 그 내부에 html 파일(실제내용)을 보여줌



