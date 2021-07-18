import serial

import pyautogui

ArdSerial = serial.Serial('com32', 9600)

while 1:
    incomingData = str (ArdSerial.readline())
    print(incomingData)

    if('next' in incomingData):
        pyautogui.hotkey('ctrl', 'pgdn')

    if ('previous' in incomingData):
        pyautogui.hotkey('ctrl', 'pgup')

    if('down' in incomingData):
        pyautogui.scroll(-100)

    if('up' in incomingData):
        pyautogui.scroll(100)

    if('change' in incomingData):
        pyautogui.keyDown('alt')
        pyautogui.press('tab')
        pyautogui.keyUp('alt')


    incomingData = ""
