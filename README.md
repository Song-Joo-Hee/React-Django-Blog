# 리액트와 장고를 이용한 풀스택 블로그
## 2021-11-26 
**1. Django 및 React.js 설치**
* Backend / Frontend 따로 폴더를 생성하여 폴더 안에 장고와 리액트를 각각 설치하였다.\
**2. Django 가상환경 설정** 
* 가상환경을 위한 venv 폴더를 생성하여 가상환경을 활성화해주었다. 
**3. PostgreSQL 데이터베이스 생성**
* 장고와 연결해줄 데이터베이스를 psql을 통해 생성하였다. (이름 : blog)
**4. Django 프로젝트 및 앱 생성**
* 장고 명령어를 통해 프로젝트를 생성하였고, 해당 프로젝트 안에 앱을 생성하였다. (프로젝트 이름 : anonymous_blog, 앱 이름 : blog) 
**5. Django settings.py 파일 수정** 
* 장고와 리액트의 연동을 위한 설정을 추가하였다. (corsheaders, dirs 경로 변경, rest_framework 설정 추가) 
* 데이터베이스는 포스트그레로 설정을 수정하였다.  
* 정적파일과 미디어파일을 위한 경로 설정을 추가하였다. 
**6. Django urls.py 파일 수정**
* api 권한 / summernote 사용 가능 / 앱 blog url 포함 / react router 경로 추가 / 미디어 파일 경로 추가를 위한 url들을 생성해주었다. 
**7. Django 'blog' models.py 테이블 추가**
* 메인 테이블인 'blogpost'를 생성하여 각 필드에 맞는 타입을 설정해주었다.
* 카테고리 필드는 하나를 선택할 수 있도록 models.TextChoices를 사용하였다.  
* slug 생성을 위해 각 게시물마다 고유한 url을 만들어주는 함수를 생성하였다.
**8. Django 'blog' admin.py 파일 수정**
* Django admin 화면에서 models.py에서 만들어준 테이블을 보기 쉽게 관리할 수 있도록 설정해주었다.
*  Django admin 화면에서 models.py에서 만들어준 테이블에 값을 등록할 수 있도록 설정해주었다.
**9. Django 'blog' serializer.py 파일 추가**
* 리액트에서 데이터를 가져오기 위해, 데이터를 json 형식으로 변경해주는 serializer.py 파일을 추가하였다.
**10. Django 'blog' views.py 파일 수정**
* 첫번째, 전체 게시글을 볼 수 있는 view를 생성해주었다. (ListAPIView)
* 두번째, 하나의 게시글을 상세조회 할 수 있는 view를 생성해주었다. (RetrieveAPIView)
* 세번째, 'featured'에 체크를 한 게시글만 조회할 수 있는 view를 생성해주었다. (ListAPIView)
* 네번째, 카테고리별로 게시글을 조회할 수 있도록 카테고리를 생성해주는 view를 생성해주었다. (ListAPIView)
**11. Django 'blog' urls.py 파일 추가**
* 각 view에 맞는 url을 각각 생성해주었다. 
**12. Django admin 화면을 통한 게시글 생성**
* admin 화면에 접근할 수 있도록 user 정보를 생성해주었다.
* admin 화면에서 각 필드를 채워 게시글을 등록하였다. 
**13. Postman을 통한 각 url 검증** 
* postman을 통해 각 url이 실제로 원하는 데이터를 보여주는지를 검증하였다. 

## 2021-11-30
**1. frontend(React.js) 뼈대 만들기** 
* 불필요한 기존 파일들을 제거 후, src 폴더에 하위 폴더들을 생성하여 화면을 구성하는데에 필요한 파일들을 생성하였다.
**2. React.js 'components' 폴더 내 파일 수정**
* components 폴더에는 각 화면을 구성하는 파일들이 담겨져있다.
* 파일 내 구조는 함수 컴포넌트를 사용하여 첨부 이미지와 동일하게 추가하였다. 
![image](https://user-images.githubusercontent.com/95834067/145533550-b1a70711-5150-4b50-afed-c27ce4c5dc78.png)
**3. React.js App.js 파일 수정**
* 각 화면에 맞는 url을 생성하기 위해 BrowserRouter, Route, Routes 태그를 이용하여 파일을 수정하였다. 
**4. React.js bootstrap 라이브러리 반영(index.html / Navbar.js)**
* bootstrap 라이브러리를 사용하기 위해 bootstrap 사이트를 참고하여 index.html 파일에 전체적인 스타일을 설정해주었다. 
* Navbar.js 파일에서 부트스트랩 코드를 참고하여 Link 및 NavLink를 이용하여 이동하는 화면과 연결시켜주었다.
**5. React.js bootstrap 라이브러리 반영(Home.js)**
* Home.js 에 부트스트랩 블로그 버전을 참고하여 코드를 추가해주었다. 
**6. React.js Blog.js 파일 수정**
* axios를 통해 게시글 목록과 featured 게시글 목록을 보여주는 백엔드의 url과 연결시켜주었다. (이 때, 게시글 목록은 테이블의 전체 데이터를 보여주도록 하고, featured 게시글 목록은 하나의 데이터만 보여주도록 한다.)
* map을 통해 실제 데이터와 매핑하여 리스트에 담아주었다. 
* 부트스트랩을 이용하여 화면을 정돈해주었다. 

## 2021-12-02
**1. React.js BlogDetail.js 파일 수정**
* 게시글 중 하나를 클릭하면 그에 대한 전체 내용을 볼 수 있게 코드를 수정하였다. 
* useParams를 이용하여 고유한 id를 받아와서 url를 매칭한다. 
**2. React.js Category.js 파일 수정**
* 카테고리 별로 게시글을 볼 수 있도록 수정하였다.
* useParams를 이용하여 카테고리 별로 고유한 id를 받아와서 url를 매칭한다. 
* blog.js와 동일한 폼으로 구성하였다. 

