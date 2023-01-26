# poetry install
[참고자료](https://www.digitalocean.com/community/tutorials/how-to-install-poetry-to-manage-python-dependencies-on-ubuntu-22-04)

다음 명령어를 입력하기
```
curl -sSL [https://install.python-poetry.org](https://install.python-poetry.org/) | python3 -
```

Bash가 있는 Ubuntu에서는 다음과 같이 선호하는 텍스트 편집기 ~/.bashrc를 사용하여 파일을 열기
```
nano ~/.bashrc
```

파일 끝에 다음 줄을 추가
```
export PATH="/home/sammy/.local/bin:$PATH"
```

세션에 변경사항 추가하기
```
source ~/.bashrc
```

poetry 버전 확인해보기
```
poetry --version
```

# poetry project setting
```
poetry new 프로젝트명
cd 프로젝트명
```

# Install Django on Ubuntu
```
sudo apt-get update
sudo apt-get install python3
python3 -V
```

```
poetry new test_poetry
cd test_poetry
ls
nano pyproject.toml
poetry add requests
```
```
sudo apt install python3-django
django-admin --version
poetry shell
poetry add Django
django-admin startproject config . 
ls -al
python [manage.py](http://manage.py/) runserver
```

# 포트 변경하기
1. cmd창에서 pem 파일 있는 경로로 이동
2. ssh -i 키 입력하기
3. cd 내가 설정한 프로젝트 이름 ex) cd test_poetry
4. poetry shell
5. cd config
6. ls 입력해서 확인해보자
7. 편집기로 settings.py 열기 ex) vi settings.py
8. 처음엔 명령모드니까 esc 누르고 i(insert) 눌러서 수정모드로 변경
```ALLOWED_HOSTS = [’내 아이피’, ‘*’] ``` esc 누르고 :wq
9. 상위 폴더로 가기 ```cd ..```
10. aws 가서 보안그룹 설정
11. 인바운드 규칙 편집
규칙추가 > 사용자 지정 TCP > 포트범위 8000 > 소스 0.0.0.0./0 


1. python [manage.py](http://manage.py) migrate
2. python [manage.py](http://manage.py) runserver 0:8000
3. 주소창에 내아이피:8000 입력하기
[http://3.35.47.255:8000/](http://3.35.47.255:8000/)
