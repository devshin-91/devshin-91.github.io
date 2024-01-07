---
title: "[아나콘다]jupyter notebook 과 spyder"
date: 2024-01-07
---

# 1. 작성 동기
  1. 용도 별로 필요한 에디터가 있고 이를 사용하는 법을 잊지 않기 위해서 기록할 필요가 있다.
  2. 일반적인 경우 vscode로만으로도 충분하지만 쓰는 용도에 따라서는 다른 에디터도 쓸 필요가 있다.

# 2. 필요성
  1. 사실 vscode만으로도 에디터는 충분하긴 하다.
  2. 그 이유는 수많은 익스텐션이 있어서 편의성이 굉장히 좋기 때문이다.
  3. 하지만 본인이 쓰고자 하는 용도에 따라서는 다른 에디터가 유용할 수 있다.
  4. 일단 내가 추천하는 에디터는 jupyter notebook 과 spyder이다.
  5. 먼저 Jupyter의 경우 google colab처럼 code 별로 실행이 가능하고 마크다운 문서를 작성하기 편하다.
  6. 이러한 점에서 변수 제어, 중간 결과 훓기, 코드 공유 등에 유용하게 쓰인다.
  7. spyder의 경우, 코드 실행시 나타나는 변수와 출력된 이미지 등의 정보를 볼 수 있다.
  8. 이러한 점을 활용하면 디버깅이나 이미지 분석에 유용하게 쓸 수 있다. 

# 3. 과정

1. Jupyter notebook

    1.0 conda 가상환경 활성화

    ```cmd
    conda activate <가상환경>
    ```

    1.1 설치 명령어

    ```cmd
    pip install notebook
    ```

    1.2 jupyter notebook 실행 및 link

    - jupyter notebook 실행 : 프롬프트에 명령어 `jupyter notebook` 입력 => jupyter 접속 링크와 함께 브라우저 창에 jupyter notebook의 인터페이스 등장

    - jupyter 접속 link : http://localhost:8888/?token=<토큰값> 또는 http://127.0.0.1:8888/?token=<토큰값>

      ![jupyter notebook 접속 링크](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/1.link.jpg)

    1.3 인터페이스 확인 및 파이썬 노트북 생성

    - 인터페이스의 tree : 인터페이스는 트리의 최상단으로 `/`를 보여줌. 트리의 최상단의 경로는 jupyter notebook 명령을 실행한 당시의 아나콘다 프롬프트 상 경로
 
    - 파이썬 노트북 생성 : 인터페이스 상단의 우측 -> New 버튼 -> Python 3 (ipykernel) 클릭

      ![인터페이스 화면](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/2.interface.jpg)

    1.4 키보드 단축키

    - 단축키 옵션 확인 경로 : 코드 편집화면 상단 `Help` 탭 -> `Keyboard Shortcuts` 클릭

      ![키보드 단축키 경로](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/3.keyboard_shortcuts1.jpg)

    - 키보드 단축키 : 키보드 단축키는 크게 명령모드와 편집모드로 나뉜다. 코드가 작성되는 네모 박스를 셀이라고 할 때, 셀 밖에서 작동하는 것이 명령모드, 셀 안에서 작동하는 것이 편집모드이다.

      ![키보드 단축키](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/3.keyboard_shortcuts2.jpg)

    - 명령모드 : 셀에서 `ESC`를 누르면, 마우스 커서가 사라지면서 명령모드가 활성화된다. 주로 셀을, 조작 생성하는 데 사용된다.

    - 편집모드 : 셀에서 `Enter`를 누르면,셀 내부에서 마우스 커서가 나오면서 편집모드가 활성화된다. 주로 셀 내부에서 동작하는 단축키로, 마우스 커서 및 코드를 조작하는 데 사용된다.

    ※ 유의사항 : Jupyter notebook은 Google Colab과 사용방법이 유사하기 때문에 금방 익숙하게 다룰 수 있다.

2. Spyder

    2.0 conda 가상환경 활성화

    ```cmd
    conda activate <가상환경>
    ```

    2.1 Spyder 설치

    - 설치 방법 : 크게 두 가지 방법으로 공식 홈페이지에 가서 설치파일을 다운받아 설치하거나 아나콘다 가상환경을 만들 때, python과 함께 spyder를 설치한다. 

      ※ 주의사항 : 이 다음에 이어지는 방식은 후자 방식의 설치 기준으로 진행된다.

    2.2 Spyder 실행 및 인터페이스 확인

    - Spyder 실행 : Anaconda prompt에서 `spyder`명령어 입력

      ![Spyder 명령어](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/4.spyder.jpg)
    
    - 인터페이스 확인 : 좌측 팔레트는 코드 창, 상단 우측 팔레트는 변수, Plot 확인, 디렉토리의 File 등 을 확인할 수 있는 정보창, 하단 우측 팔레트는 해당 가상환경이 쓰는 버전의 Ipython console 이다. 

      ![Spyder 인터페이스](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/4.spyder_interface.jpg)

    2.3 폴더 경로 및 파이썬 파일 생성

    - Spyder의 기본 경로

      ```markdown
       c:\Users\<현재 사용자명> 
      ```

    - 파이썬 파일 생성 : 상단 우측의 폴더 아이콘 클릭 -> 원하는 폴더 경로 선택 -> 상단 좌측의 문서 아이콘 클릭 -> 원하는 경로의 untitled0.py 생성

      ![파이썬 파일 생성](https://devshin-91.github.io/fig/hard_work/jupyter_spyder/5.python_path.jpg)

# 4. 추가사항
  1. 그 외에도 많은 에디터들이 있지만 그건 개인 기호에 맞게 설치해서 사용해보면 좋을 것 같다.
  2. 버전 관리나 패키지 활용면에서는 PyCharm도 좋은 것 같은 데, 잘 쓰지 않아서 필요한 사람은 익혀두는 것도 좋다고 생각한다. 

# 5. 참고
  1. jupyter notebook 설치 및 실행 : https://jupyter.org/install
  2. spyder 홈페이지 : https://www.spyder-ide.org/