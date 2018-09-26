# scrabble
Simple game of scrabble

import time

def ss():

    #opening up the text files which contain all English that will be accepted
    with open('english_words.txt') as file:
        data=file.read()
        english_dict=data.splitlines()

    name=input('What is your name? ')
    initial_message= input(('''
           Hello %s. In a few seconds the letters of the alphabet will
           appear. Each letter is assigned to a number. You have 20 seconds
           to type as many words as you can, to get the highest number possible. When
           you Press enter the game will begin.
           ''')%(name))
    
    if len(initial_message)!=0:
        pass

    #dictionary which the user uses to get the highest score possible
    score = {"a": 1, "c": 3, "b": 3, "e": 1, "d": 2, "g": 2, 
         "f": 4, "i": 1, "h": 4, "k": 5, "j": 8, "m": 3, 
         "l": 1, "o": 1, "n": 1, "q": 10, "p": 3, "s": 1, 
         "r": 1, "u": 1, "t": 1, "w": 4, "v": 4, "y": 4, 
         "x": 8, "z": 10}
    print (score)

    words_used=[] #list which is used to see if user has repeated any words
    total=0 #records total score the user has gained

    #the game last for 20 seconds 
    while time.clock()<20:
        input_word=input('Enter a word: ')
        input_word=input_word.lower() #puts the user input in lower case as all words in the txt file are lower case
     
        
        
        if input_word not in words_used and len(input_word)!=0:
            words_used.append(input_word)

           

            if input_word in english_dict:
                for letters in input_word:
                    total+=score[letters]


            else:
                print ('That word is not in the English dictionary. Try again!')
            print ('Total Score= ' + str(total))

        elif len(input_word)==0:
            print ('You need to input a word!. Try again')

        else:
            print ('You already entered that word. Try again!')
    print(('time is up! Your final score is %d.') %(total))
    

    #all_of_users_totals=open('totals.txt', 'r+')
    #all_of_users_totals.write(str(total))
    #all_of_users_totals.close()
    
ss()


        
