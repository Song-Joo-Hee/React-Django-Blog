# 리액트와 장고를 이용한 풀스택 블로그
## 2021-11-26 
1. Django 및 React.js 설치 
* Backend / Frontend 따로 폴더를 생성하여 폴더 안에 장고와 리액트를 각각 설치하였다.
2. Django 가상환경 설정 
* 가상환경을 위한 venv 폴더를 생성하여 가상환경을 활성화해주었다. 
3. PostgreSQL 데이터베이스 생성
* 장고와 연결해줄 데이터베이스를 psql을 통해 생성하였다. (이름 : blog)
4. Django 프로젝트 및 앱 생성
* 장고 명령어를 통해 프로젝트를 생성하였고, 해당 프로젝트 안에 앱을 생성하였다. (프로젝트 이름 : anonymous_blog, 앱 이름 : blog) 
5. Django settings.py 파일 수정 
* 장고와 리액트의 연동을 위한 설정을 추가하였다. (corsheaders, dirs 경로 변경, rest_framework 설정 추가) 
* 데이터베이스는 포스트그레로 설정을 수정하였다.  
* 정적파일과 미디어파일을 위한 경로 설정을 추가하였다. 
6. Django urls.py 파일 수정
* api 권한 / summernote 사용 가능 / 앱 blog url 포함 / react router 경로 추가 / 미디어 파일 경로 추가를 위한 url들을 생성해주었다. 
7. Django 'blog' models.py 테이블 추가
* 메인 테이블인 'blogpost'를 생성하여 각 필드에 맞는 타입을 설정해주었다.
* 카테고리 필드는 하나를 선택할 수 있도록 models.TextChoices를 사용하였다.  
* slug 생성을 위해 각 게시물마다 고유한 url을 만들어주는 함수를 생성하였다.
8. Django 'blog' admin.py 파일 수정
* Django admin 화면에서 models.py에서 만들어준 테이블을 보기 쉽게 관리할 수 있도록 설정해주었다.
*  Django admin 화면에서 models.py에서 만들어준 테이블에 값을 등록할 수 있도록 설정해주었다.
9. Django 'blog' serializer.py 파일 추가
* 리액트에서 데이터를 가져오기 위해, 데이터를 json 형식으로 변경해주는 serializer.py 파일을 추가하였다.
10. Django 'blog' views.py 파일 수정
* 첫번째, 전체 게시글을 볼 수 있는 view를 생성해주었다. (ListAPIView)
* 두번째, 하나의 게시글을 상세조회 할 수 있는 view를 생성해주었다. (RetrieveAPIView)
* 세번째, 'featured'에 체크를 한 게시글만 조회할 수 있는 view를 생성해주었다. (ListAPIView)
* 네번째, 카테고리별로 게시글을 조회할 수 있도록 카테고리를 생성해주는 view를 생성해주었다. (ListAPIView)
11. Django 'blog' urls.py 파일 추가
* 각 view에 맞는 url을 각각 생성해주었다. 
12. Django admin 화면을 통한 게시글 생성
* admin 화면에 접근할 수 있도록 user 정보를 생성해주었다.
* admin 화면에서 각 필드를 채워 게시글을 등록하였다. 
13. Postman을 통한 각 url 검증 
* postman을 통해 각 url이 실제로 원하는 데이터를 보여주는지를 검증하였다. 
