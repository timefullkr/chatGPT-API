# Step #1 
# chatGPT-API 사용 채팅 기본(터미널 사용) 실습

### cursorAI를 열고 -> 폴더열기 메뉴로 > 작업할 폴더를 연다 > 이 폴더가 **최상위 폴더**가 된다..
### 상위 최상위 폴더에서 chatGPT-01를 만든다.
### chatGPT-01 폴더를 클릭(선택)한다.
### .env 파일을 생성하고 chatGPT API .env 파일에 key 설정한다.
```
openai_api_key="sk-sbNY***************jxNgOLCrbB"
```
### main.py 파일을 생성하고 이를 연다.
- Python 확장 프로그램이 설치되지 않는 경우는 왼쪽 아래에 이를 설치하라는 창이 나온면 이를 설치하고 설치가 완료되면 설치 텝창을 닫는다.
- 이를 설치 할수 없으면 더이상 진행할 수 없다.


### main.py 에서 ctrl +k 입력하여 다음 과 같은 내용을 입력하여 코드를 생성한다.
```
chatgpt API로 채팅하는 코드
api key는 env 사용
모델은 gpt-4o
```
- 생성된 코드 예시
```
import os
from openai import OpenAI
from dotenv import load_dotenv
# pip install openai python-dotenv
# .env 파일에서 환경변수 로드
load_dotenv()

# OpenAI API 클라이언트 초기화
client = OpenAI(api_key=os.getenv('OPENAI_API_KEY'))

def chat_with_gpt(message):
    try:
        # API 요청
        response = client.chat.completions.create(
            model="gpt-4",
            messages=[
                {"role": "user", "content": message}
            ]
        )
        
        # 응답 반환
        return response.choices[0].message.content
    except Exception as e:
        return f"오류가 발생했습니다: {str(e)}"

# 사용 예시
if __name__ == "__main__":
    while True:
        user_input = input("질문을 입력하세요 (종료하려면 'q' 입력): ")
        if user_input.lower() == 'q':
            break
            
        response = chat_with_gpt(user_input)
        print("\nGPT 응답:", response, "\n")


```
### 생성된 코드를 반영한다.
### 코드 상단에 import 또는 from 경고 표시가 있으면 해당 라이브러리는 설치한다.
- 라이브러리는 설치 방법을 모르면 터미널 창을 열고  ctrl +k -> "main.py에 필요 라이브러리 설치 명령어" 입력하면 터밀널에 명령어가 니오면 엔터친다.
```
pip install openai python-dotenv
```
### 이제 실행(F5)하고 채팅을 해본다. 

# Step #2 
## chatGPT-API 채팅 html GUI 사용 채팅하기 만들기 실습
### 탐색기에서 상위 최상위 폴더를 선택하고 chatGPT-02 폴더를 만든다. Step #2는 "chatGPT-02"폴더를 사용하다.
### chatGPT-01 폴더의 .env, main.py 파일을 복사하여 chatGPT-02 폴더에 붙여넣기를 한다.
!(/images/screen01.png)



