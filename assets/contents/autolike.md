---
title: facebook auto love react
description: facebook auto love react
header: FB AUTOLIKE
permalink: /autolike
---



















```
import pynput
```


```
from pynput.keyboard import Key, Controller
import time

keyboard = Controller()
time.sleep(1)
while True:
    keyboard.press('j')
    keyboard.release('j')

    keyboard.press('l')
    keyboard.release('l')

    keyboard.press(Key.right)
    keyboard.release(Key.right)

    keyboard.press(Key.enter)
    keyboard.release(Key.enter)

    time.sleep(1)
    
 ```   
