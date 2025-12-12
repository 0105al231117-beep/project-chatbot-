# project-chatbot-
import pyautogui
import time
import pyperclip
from openai import OpenAI

client = OpenAI(
  api_key="" ) 

time.sleep(2)

pyautogui.click(993 , 1047)
time.sleep(3)

pyautogui.moveTo(871,210)
pyautogui.dragTo(1879,902 , duration = 0.3 , button="left")
time.sleep(3)

pyautogui.hotkey("ctrl" , "c")
time.sleep(3)
pyautogui.click(885,242)

clip_text = pyperclip.paste()

print("you chat with naman:")
print(clip_text)


completion = client.chat.completions.create(
  model="gpt-5.1",
  messages=[
    {"role": "developer", "content": "You are a person name harry who speak hindi as well english . he is from india and is a coder . You analyze chat history and pretend to be harry and respond like harry"},
    
    {"role": "user", "content": clip_text}
  ]
)

response = completion.choices[0].message.content
pyperclip.copy(response)

pyautogui.click(18008, 1328)
time.sleep(3)

pyautogui.hotkey("ctrl" , "v")
time.sleep(2)
pyautogui.press("enter")

