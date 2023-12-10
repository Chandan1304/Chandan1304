
import random

word_list=["apple","pappay","tomato","pomato"]
chosen_word=random.choice(word_list)
print(chosen_word)
lives=int(len(chosen_word))
display=[]
for i in range(len(chosen_word)):
    display +='_'
print(display)
guess=False
while not guess:
    guess_word=input("enter a guess word:")
    for position in range(len(chosen_word)):
        letter=chosen_word[position]
        if letter==guess_word:
            display[position]=guess_word
            
    if guess_word not in chosen_word:
        lives-=1
        if lives==0:
            guess=True
            print(" you lose")
    print("num of lives",lives)
    
    if  '_'  not in display:
        guess=True
        print("congradulations you win")            
        
    print("you guessed letter",display)
