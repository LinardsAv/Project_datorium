## Guessing game
### Saturs 

#### 1. Aprakstītā spēle
#### 2. Spēles kods
Dators nejauši ģenerē vienu skaitli no 1 līdz 100. Tālāk, piedāvā spēlētājam uzminēt to skaitli. Un t.t.

Spēles loģika ir labi aprakstīta sājā kodā:
```py
import random
import time
import os

def main(): #definīcija ar kuras palīdzību var veidot loopus
    num = random.randint(1,100) #Ģenerē skaitli no 1-100
    guess = int(input("Mini skaitli...\n")) #\n ieliek tekstu jaunā rindā
    tried = []
    while guess != num:
        tried.append(guess)
        if guess > num:
            guess = int(input("Par augstu, mēģini atkal\n"))
        else:
            guess = int(input("Par zemu, mēģini atkal\n"))
    tried.append(guess)
    if len(tried) == 1:
        print("Urrā ar pirmo")
        print(f"Tava vesture {tried}")
    else:
        print(f"Tu beidzot atbildēji {num} pēc {len(tried)} mēģinājumiem!") #f ļauj vieglāk ielikt mainīgos teksta vidū
        print(f"Tava vesture {tried}")
    again = input("Mēģināsi atkal? (y/n)\n") 
    if again == "y":
        time.sleep(0.5) #0.5 sekunžu pauze
        main()
    else:
        print("Paldies par spēli!") 
main()
```
