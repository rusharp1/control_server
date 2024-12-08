<img src="https://capsule-render.vercel.app/api?type=waving&amp;color=BDBDC8&amp;height=150&amp;section=header">

# Control server

> python 과 shell script를 사용하여 원격으로 서버를 시작, 중지, 재시작 하는 애플리케이션.

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https://github.com/rusharp1/control_server&count_bg=%233B3B3B&title_bg=%23B178BE&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)

## 1. control_server

### 1\. 프로젝트 목록
#### 1. 프로젝트 개요 (Introduction)
   - 이 프로젝트는 Python 과 Shell script 를 사용하여 원격 서버에서 서비스를 시작, 중지, 또는 재시작하는 Python 애플리케이션 입니다.
PyQt Gui 를 사용하여 사용자로부터 IP주소, 액션 (서비스 시작/중지/재시작), 서비스 이름, 사용자 이름, sudo 비밀번호를 입력받고,
이를 control_server.sh 스크립트를 통해 원격 서버에서 실행합니다.
#### 2. 파일 구조 및 기능 설명
1. 파일 구조
   ```
    control_server/
   ├── control_server.py   # PyQt5 GUI 애플리케이션 코드
   └── control_server.sh   # Bash 스크립트 (원격 서버에서 서비스 관리)
   ```

2. control_server.py
   - PyQt를 기반으로 작성된 GUI애플리케이션
   - 사용자 입력을 받아 원격 서버에서 서비스를 제어하기 위해 control_server.sh 스크립트 호출
   - IP, 액션, 서비스, 이름, 사용자 이름, 비밀번호 등 유효성 검사 진행.
   - GUI를 통해 명령 실행 및 결과를 출력.

3. control_server.sh
   -  원격 서버에 SSH를 통해 접속하고 systemctl 명령어를 실행.
   -  sshpass 를 사용하여 비밀번호 자동으로 입력.
   -  명령 실행 결과를 표준 출력 및 에러로 변환

### 3\. 사전 요구사항 \(Prerequisites\)
#### 1. 필수 환경
* Python 3.8 이상
* PyQt5 설치
* sshpass 설치

### 4\. 설치 방법 \(Installation\)
1. PyQt5 를 설치합니다.
    ```
    pip install pyqt5
    ```
2. Homebrew 를 사용하여 sshpass를 설치합니다..
    ```
    brew install sshpass
    ```
3. 프로젝트를 로컬에 클론합니다.
    ```
    git clone -b master https://github.com/rusharp1/control_server.git
    ```
    ↳ 이 때, control_server.py 와 control_server.sh가 같은 디렉토리에 위치해야 합니다.
3. 해당 프로젝트 위치로 이동합니다.
    ```
    cd ./control_server/control_server
    ```
5. python 파일을 실행합니다.

    ```
    control_server.py
    ```
 
### 5\. 사용 방법 \(Directions\)

1. Server IP: 원격 서버의 IP 주소를 입력합니다.
2. Action: start, stop, restart 중 하나를 선택합니다.
3. Sudo Password: 원격 서버에서 sudo 명령을 실행하기 위한 비밀번호를 입력합니다.
4. Service Name: 관리하려는 서비스의 이름을 입력합니다 (예: nginx, apache2 등).
5. User Name: 원격 서버에 로그인할 때 사용할 사용자 이름을 입력합니다.
6. Run 버튼을 클릭하면, 입력한 정보가 control_server.sh 스크립트를 통해 실행되며, 결과가 출력됩니다.\

   ex) 아래는 192.168.0.1 에서 nginx 프로그램을 서비스 시작하는 방법입니다. {} 내 정보는 해당 서버에 맞게 설정해야 합니다.
      - Server IP: 192.168.0.1
      - Action: start
      - Sudo Password: {your_password}
      - Service Name: nginx
      - User Name: {user_name}


### 6\. 주의 사항 (caution)

1. sshpass는 비밀번호를 평문으로 처리하는 도구입니다. 보안에 민감한 환경에서는 사용을 지양할 수 있습니다.
2. 원격 서버의 사용자 권한에 따라 sudo 명령어가 정상적으로 실행되지 않을 수 있습니다. 원격 서버에서 해당 권한을 부여해야 합니다.
3. 이 프로그램은 기본적으로 Macos → Linux/Unix 기반 서버에서 동작하도록 설계되었습니다. 다른 운영 체제에서는 정상적으로 동작하지 않을 수 있습니다.

## 2. LICENSE

이 프로젝트는 [MIT License](LICENSE) 에 따라 라이선스가 부여됩니다.

<img src="https://capsule-render.vercel.app/api?type=waving&amp;color=BDBDC8&amp;height=150&amp;section=footer">
