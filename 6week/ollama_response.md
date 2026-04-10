# 가장 기본적인 텍스트 생성
response = ollama.generate(
    model="gemma3:4b",
    prompt="파이썬이란 무엇인가요? 한 문장으로 설명해주세요."
)

# 결과 확인
print(response["response"])
```

이 코드는 Ollama API를 사용하여 Gemma3 4B 모델에 "파이썬이란 무엇인가요? 한 문장으로 설     
명해주세요."라는 프롬프트를 보내고, 모델이 생성한 응답을 출력합니다.

**실행 결과 (예시):**

```
파이썬은 읽기 쉽고 배우기 쉬운 고수준 프로그래밍 언어로, 다양한 분야에서 활용될 수 있습     
니다.
```

**코드 설명:**

*   `import ollama`: Ollama 라이브러리를 가져옵니다.
*   `response = ollama.generate(...)`:  `ollama.generate()` 함수를 사용하여 텍스트를 생     
성합니다.
    *   `model="gemma3:4b"`: 사용할 모델을 지정합니다. 여기서는 Gemma3 4B 모델을 사용합     
니다.
    *   `prompt="파이썬이란 무엇인가요? 한 문장으로 설명해주세요."`: 모델에 제공할 프롬     
프트를 지정합니다.
*   `print(response["response"])`: `response` 딕셔너리의 "response" 키에 해당하는 값을      
출력합니다.  `response` 딕셔너리는 Ollama API에서 반환된 JSON 응답을 포함합니다. 이 값은    
 모델이 생성한 텍스트입니다.

**참고:**

*   Ollama를 사용하려면 먼저 Ollama를 설치하고 실행해야 합니다.
*   이 코드를 실행하기 전에 `ollama` 라이브러리가 올바르게 설치되어 있는지 확인하세요.      
 `pip install ollama` 명령어를 사용하여 설치할 수 있습니다.
*   Ollama 서버가 실행 중이어야 합니다.
*   결과가 약간씩 다를 수 있습니다.  Ollama 모델의 특성상, 동일한 프롬프트를 사용하더라     
도 약간 다른 답변이 나올 수 있습니다.



# 대화형 API — 메시지 목록을 전달
response = ollama.chat(
    model="gemma3:4b",
    messages=[
        {
            "role": "user",
            "content": "빅데이터의 3V에 대해 설명해주세요."
        }
    ]
)

# 응답 출력
print(response["message"]["content"])
```

이 코드는 Ollama의 대화형 API를 사용하여 Gemma3 4B 모델과 상호작용합니다.  `ollama.chat()` 함수는 메시지 목록을 입력으로 받아 모델의 응답을 생성합니다.

**실행 결과 (예시):**

```
빅데이터는 Volume(규모), Velocity(속도), Variety(다양성)의 3가지 특징을 가지고 있습니다.  대용량의 데이터, 빠른 데이터 생성 속도, 그리고 다양한 형태의 데이터를 의미합니다.
```

**코드 설명:**

*   `import ollama`: Ollama 라이브러리를 가져옵니다.
*   `response = ollama.chat(...)`: `ollama.chat()` 함수를 사용하여 대화형 응답을 생성합니다.
    *   `model="gemma3:4b"`: 사용할 모델을 지정합니다. 여기서는 Gemma3 4B 모델을 사용합니다.
    *   `messages=[...]`:  모델에 전달할 메시지 목록을 지정합니다.  각 메시지는 딕셔너리 형태로 표현됩니다.
        *   `{"role": "user", "content": "빅데이터의 3V에 대해 설명해주세요."}`:  사용자 메시지를 나타냅니다.
            *   `"role": "user"`: 메시지 역할을 지정합니다.  "user"는 사용자 메시지임을 나타냅니다.
            *   `"content": "빅데이터의 3V에 대해 설명해주세요."`: 메시지 내용을 나타냅니다.
*   `print(response["message"]["content"])`: `response` 딕셔너리의 "message" 키에 해당하는 딕셔너리에서 "content" 키에 해당하는 값을 출력합니다.  `response` 딕셔너리는 Ollama API에서 반환된 JSON 응답을 포함합니다.

**핵심 변경 사항:**

*   `ollama.generate()` 대신 `ollama.chat()` 함수를 사용합니다.
*   프롬프트 문자열 대신 메시지 목록을 전달합니다.  메시지 목록은 사용자 메시지와 모델의 응답을 체인처럼 연결하여 대화형 인터랙션을 구성하는 데 사용됩니다.
*   Ollama API는 대화형 API를 지원하며, 이전의 `generate()` 함수는 단일 프롬프트를 사용하는 데 적합했습니다.  대화형 API는 대화의 흐름을 관리하고 이전 메시지를 기억하여 더욱 자연스러운 응답을 생성하는 데 도움이 됩니    
다.


# 시스템 프롬프트로 AI의 역할 설정
messages = [
    {
        "role": "system",
        "content": "당신은 친절한 파이썬 튜터입니다. 대학생 눈높이에 맞춰 쉽게 설명해주세요. 답변은 3문장 이내로 간결하게 해주세요."
    },
    {
        "role": "user",
        "content": "리스트와 튜플의 차이가 뭐예요?"
    }
]

# 첫 번째 질문
response = ollama.chat(model="gemma3:4b", messages=messages)
assistant_reply = response["message"]["content"]
print("AI:", assistant_reply)

# AI의 답변을 대화 기록에 추가
messages.append({"role": "assistant", "content": assistant_reply})

# 두 번째 질문 (이전 대화를 기억함)
messages.append({"role": "user", "content": "그러면 딕셔너리는요?"})
response = ollama.chat(model="gemma3:4b", messages=messages)
print("\nAI:", response["message"]["content"])
```

이 코드는 Ollama를 사용하여 대화형 튜터를 구현하는 예시입니다. 시스템 프롬프트를 사용하여 AI에게 특정 역할을 부여하고, 이전 대화 내용을 기억하여 일관성 있는 답변을 제공합니다.

**실행 결과 (예시):**

```
AI: 리스트와 튜플은 둘 다 순서가 있는 자료구조이지만, 리스트는 변경 가능(mutable)하고 튜플은 변경 불가능(immutable)합니다. 리스트는 요소 추가, 삭제, 변경이 가능하지만 튜플은 한 번 생성되면 수정할 수 없습니다. 따라서    
 리스트는 데이터 수정이 필요할 때 사용하고, 튜플은 데이터의 안정성을 보장해야 할 때 사용합니다.

AI: 딕셔너리는 키-값 쌍으로 이루어진 자료구조입니다. 각 키는 고유해야 하며, 딕셔너리의 요소에 접근하려면 키를 사용합니다. 딕셔너리는 매우 유연하며, 데이터 추가, 삭제, 수정이 쉽습니다.
```

**코드 설명:**

1.  **시스템 프롬프트 설정:**
    *   `messages` 리스트는 대화의 시작을 위한 메시지 목록입니다.
    *   첫 번째 메시지는 `{"role": "system", "content": ...}` 형태로 AI에게 역할과 지침을 제공합니다.  여기서는 AI가 파이썬 튜터 역할을 수행하고, 대학생 수준으로 설명하며, 답변은 3문장 이내로 간결하게 해야 한다고 지    
정합니다.

2.  **첫 번째 질문:**
    *   `ollama.chat()` 함수를 사용하여 Gemma3 4B 모델에게 질문을 던집니다.
    *   `response["message"]["content"]`를 통해 모델의 답변을 추출합니다.
    *   `print("AI:", assistant_reply)`를 통해 답변을 출력합니다.

3.  **대화 기록 업데이트:**
    *   `messages.append({"role": "assistant", "content": assistant_reply})`를 사용하여 AI의 답변을 `messages` 리스트에 추가합니다.  이렇게 하면 다음 질문에 대한 답변 생성 시 AI가 이전 대화 내용을 기억할 수 있습니다    
.

4.  **두 번째 질문:**
    *   `messages.append({"role": "user", "content": "그러면 딕셔너리는요?"})`를 사용하여 새로운 질문을 `messages` 리스트에 추가합니다.
    *   `ollama.chat()` 함수를 사용하여 모델에게 질문을 던집니다.
    *   `print("\nAI:", response["message"]["content"])`를 통해 답변을 출력합니다.  `\n`은 줄 바꿈을 의미하여 출력을 보기 좋게 합니다.

**핵심 포인트:**

*   **시스템 프롬프트:**  AI의 행동을 지시하고 역할의 핵심을 정의하는 데 중요합니다.
*   **대화 기록 관리:**  `messages` 리스트를 사용하여 이전 대화 내용을 기억하고, 더욱 자연스러운 대화 흐름을 만들 수 있습니다.  Ollama의 대화형 API는 이러한 대화 맥락을 활용하도록 설계되었습니다.
*   **메시지 역할:** `role` 속성은 메시지의 유형(user, assistant, system)을 정의하여 모델이 적절하게 응답하도록 합니다.



print("스트리밍 출력 시작:")
print("-" * 40)

# stream=True로 실시간 출력
stream = ollama.chat(
    model="gemma3:4b",
    messages=[
        {"role": "user", "content": "Streamlit이 무엇인지 5줄로 설명해주세요."}
    ],
    stream=True
)

for chunk in stream:
    # 각 청크에서 텍스트 조각을 추출하여 출력
    print(chunk["message"]["content"], end="", flush=True)

print()  # 마지막 줄바꿈
```

이 코드는 `stream=True` 옵션을 사용하여 Ollama API로부터 텍스트를 실시간으로 스트리밍 받습니다.  `ollama.chat()` 함수 호출 시 `stream=True`를 설정하면, 응답이 한 번에 반환되지 않고, 각 텍스트 조각(chunk)이 생성될 때    
마다 반복문(`for chunk in stream:`)에서 처리됩니다.

**실행 결과 (예시):**

```
스트리밍 출력 시작:
----------------------------------------
Streamlit은 Python에서 데이터 과학 및 머신러닝 애플리케이션을 빠르게 구축하고 공유할 수 있는 오픈소스 프레임워크입니다. 간단한 웹앱을 만들 수 있도록 도와주며, 다양한 데이터 시각화 도구와 통합됩니다. Streamlit은 코드    
를 수정하지 않고도 앱을 즉시 실행하고 공유할 수 있습니다.  이를 통해 데이터 과학 연구 결과를 빠르게 공유하고 협업할 수 있습니다. Streamlit은 사용자 인터페이스를 구축하기 위한 Python 코드를 작성하는 데 중점을 둡니다     
.
```

**코드 설명:**

*   `print("스트리밍 출력 시작:")` 및 `print("-" * 40)`: 스트리밍 출력이 시작됨을 알리는 메시지를 출력하고, 구분선을 표시합니다.
*   `stream = ollama.chat(...)`:  `ollama.chat()` 함수를 호출하여 텍스트를 생성하고, `stream=True`를 설정합니다.  이렇게 하면 응답이 텍스트로 즉시 반환되지 않고, 각 조각이 생성될 때마다 `stream` 객체에서 반복될 수      
있습니다.
*   `for chunk in stream:`: `stream` 객체에서 텍스트 조각을 하나씩 가져와 `chunk` 변수에 저장하고 반복합니다.
*   `print(chunk["message"]["content"], end="", flush=True)`:  각 텍스트 조각의 내용을 출력합니다.
    *   `chunk["message"]["content"]`:  `chunk` 딕셔너리에서 "message" 키에 해당하는 딕셔너리에서 "content" 키에 해당하는 값을 추출합니다.  이 값이 텍스트 조각입니다.
    *   `end=""`:  `print()` 함수가 자동으로 줄바꿈 문자를 추가하는 것을 방지합니다.  이렇게 하면 텍스트 조각들이 한 줄에 이어지도록 합니다.
    *   `flush=True`:  `print()` 함수가 버퍼링된 출력을 즉시 화면에 표시하도록 지시합니다.  이렇게 하면 텍스트 조각이 생성되는 즉시 화면에 나타납니다.
*   `print()`:  마지막 텍스트 조각이 출력된 후, 줄바꿈 문자를 추가하여 출력 형식을 정리합니다.

**주의 사항:**

*   `stream=True` 옵션을 사용하면 응답 속도가 느려질 수 있습니다.  오llama 모델이 텍스트를 생성하는 데 시간이 걸리기 때문입니다.
*   `flush=True` 옵션을 사용하면 출력 속도가 더욱 느려질 수 있습니다.  출력 버퍼가 즉시 화면에 표시되기 때문입니다.
*   실시간 스트리밍은 대화형 AI 응답을 구현하는 데 유용하지만, 응답 속도와 사용 가능한 리소스에 따라 성능이 달라질 수 있습니다.

이 코드는 Streamlit에 대한 설명을 실시간으로 생성하는 예시입니다.  이 코드를 기반으로 다른 모델이나 질문에 대해 실시간 스트리밍 기능을 사용할 수 있습니다.


