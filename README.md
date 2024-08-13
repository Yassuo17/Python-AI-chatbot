# Python-AI-chatbot
making an AI chatbot using python 
import openai
import os

openai.api_key = os.getenv("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")

def chat_with_gpt(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": prompt}]
    )
    return response.choices[0].message.content.strip()

if __name__ == "__main__":
    while True:
        user_input = input("You: ")
        if user_input.lower() in ["quit", "exit", "bye"]:
            break
        response = chat_with_gpt(user_input)
        print("Chatbot:", response)
