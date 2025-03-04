# 📌 실습 개요  
각 실습 화면은 **아래의 화살표를 클릭하여 펼쳐볼 수 있음.**  

---

## 📌 Week1 실습  

- 사용자가 업로드한 **텍스트 파일을 기반으로 AI 모델을 활용하여**  
  **요약, 번역, 이미지 생성, 음성 변환 기능을 제공**  
- OpenAI API 활용하여 각 기능 구현  

  - **요약/번역 모델**: `gpt-4o`  
  - **이미지 변환 모델**: `dall-e-3`  
  - **이미지 묘사 모델**: `GPT-4V`  
  - **음성 생성 모델**: `tts-1`  

<br>

<details>
  <summary><h4>🖥️ 실제 실행 화면 </h4></summary>
  <img src="https://github.com/user-attachments/assets/482c42a7-15ef-45a0-801d-de4c4d084562">
</details>

---

## 📌 Week2 실습  

- **멀티턴 (max=3), Cross Encoder 기반 Rerank 적용** (문서 2개 반환)  
- **OpenAI API**를 활용한 챗봇 만들기  

<br>

<details>
  <summary><h4>🔍 검색 기반 답변일 경우 </h4></summary>
  - 검색된 문서를 함께 출력  

  <img src="https://github.com/user-attachments/assets/9d77facc-a684-49bd-85ec-6184c6c9f31a">
</details>     

<details>
  <summary><h4>💬 검색 기반 답변이 아닐 경우 </h4></summary>

  - OpenAI `gpt-4o` 모델을 이용하여 대화 진행  
  - **프롬프트 템플릿** 사용하여 응답 생성  

  ```bash
  prompt_template = """
  너는 지식재산용어 챗봇 '지식재산봇'이야. 만약 누군가 네게 네가 누구냐고 물으면, 반드시 '지식재산봇'이라고 답변해.
  참고 문서를 바탕으로 답변하고, 만약 참고 문서에 있는 내용이라면 답변 끝에 '검색 기반 답변이에요'라고 붙여.
  참고 문서에 없는 내용이라면 '제 지식으로 기반한 답변이에요'라고 붙여서 답변하면 돼.
  만약 질문이 "오늘이 무슨 날짜야?"와 같이 오늘의 날짜를 묻는 경우, 현재 날짜에 해당하는 "{today_date}"이라고 정확하게 답변해줘.

  이전 대화:
  {{chat_history}}

  참고 문서: {{context}}

  질문: {{question}}
  답변:""".format(today_date=today_date)
  ```
  
  <img src="https://github.com/user-attachments/assets/6d1776ba-ad59-45ec-85db-e70f43e422a2">
</details>     
