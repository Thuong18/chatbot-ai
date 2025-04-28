# chatbot-aiimport streamlit as st
import openai

# Đặt API Key của bạn ở đây
openai.api_key = "YOUR_API_KEY" =  API Key của Im lặng

st.title("Trợ Lý A.I Cá Nhân")

# Nhập câu hỏi từ người dùng
user_input = st.text_input("Hãy nhập câu hỏi của bạn:")

if user_input:
    # Gọi OpenAI API để lấy phản hồi
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[
            {"role": "user", "content": user_input}
        ]
    )
    # Hiển thị phản hồi của A.I
    st.write("Trợ Lý A.I trả lời: ", response['choices'][0]['message']['content'])
