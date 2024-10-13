# SWE_2021_41_2024_2_week_6

## Week 4 Assignment
* [Week 4 Assignment Repository Link](https://github.com/2SeokWon/SWE_2021_41_2024_2_week_4 "Repository Week 4")
  
  ```ruby
  def isHappy(n,cycleset):
    if n in cycleset:
      return False
    else:
      cycleset.add(n)
      #print(cycleset)
    sum = 0
    while n > 0:
      num = n % 10
      sum += num ** 2
      n = n // 10
    if sum == 1:
      return True
    else:
      return isHappy(sum,cycleset)
  print(isHappy(19,cycleset = set()))
  print(isHappy(2,cycleset = set()))
  ```
* Description of my code
  1. **cycleset** : 이미 방문한 숫자들을 저장하는 set
  2. cycleset을 탐색하여 새로 넣으려는 수인 n이 존재하는지 확인한다. 존재하면 False를 반환하고 존재하지 않으면 n을 cycleset에 추가하고 계산을 계속  진행한다.
  3. n의 각 자리 숫자를 제곱하여 더한 값을 sum에 저장하고, sum이 1일 때는 True를 반환하고 sum이 그 외의 숫자일때는 isHappy() 함수를 재귀적으로 실행한다.
 
 ## Week 5 Assignment
 ```bash 
 docker exec ossp-container cat /etc/os-release
 ```
 ossp-container 컨테이너에 접속해 내부의 /etc/os-release 파일의 내용을 출력한다.

 ossp-container의 운영체제 정보를 담고 있다.
 ```
PRETTY_NAME="Ubuntu 24.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.1 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
 ```
***
 ```bash
 docker exec ossp-container git --version
 ```
 ossp-container 컨테이너의 깃 버전을 확인한다.
```
git version 2.43.0
```
***
 ```bash
 docker exec ossp-container python3 -- version
 ```
 ossp-container 컨테이너의 파이썬3 버전을 확인한다.
```
Python 3.12.3
```
***
 ```bash
docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
 ```
 ossp-container 컨테이너의 .HostConfig.Binds 속성만을 출력하도록 한다.

 이 속성은 호스트와 컨테이너 간의 바인드 마운트 정보를 갖고 있다.

 바인드 마운트는 호스트 시스템의 특정 디렉토리와 컨테이너의 특정 디렉토리를 연결하여, 파일 시스템을 공유할 수 있도록 해준다.
```
[/mnt/c/Users/seokb/Docker/ossp_host_dir:/mnt/ossp_container_dir]
```
