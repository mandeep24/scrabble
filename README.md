# scrabble
Simple game of scrabble


import time

def ss():
    with open('english_words.txt') as file:
        data=file.read()
        english_dict=data.splitlines()
    name=input('What is your name? ')
    initial_message= input(('''
           Hello %s. In a few seconds the letters of the alphabet will
           appear. Each letter is assigned to a number. You have 20 seconds
           to type as many words as you can, to get the highest number possible. Press
           enter to continue
           ''')%(name))

    if len(initial_message)!=0:
        pass
    
    score = {"a": 1, "c": 3, "b": 3, "e": 1, "d": 2, "g": 2, 
         "f": 4, "i": 1, "h": 4, "k": 5, "j": 8, "m": 3, 
         "l": 1, "o": 1, "n": 1, "q": 10, "p": 3, "s": 1, 
         "r": 1, "u": 1, "t": 1, "w": 4, "v": 4, "y": 4, 
         "x": 8, "z": 10}
    print (score)

    #user inputs a word and checks if the word is in the English dictionary
    #check()
    total=0
    while time.clock()<5:
        input_word=input('Enter a word: ')
        if input_word in english_dict:
            for letters in input_word:
                total+=score[letters]
            print ('Total Score= ' + str(total))
            input_word=input('Enter a word: ')

        else:
            print ('That word is not in the English dictionary. Try again!')
            input_word=input('Enter a word: ')
    print (('time is up! Your final score is %d') %(total))




##    word_list=input_words.split(",")
##    #print (word_list)
##    #if word_list in ...........
##
##    #if 
##    total_words=''.join(word_list)
##    total_words=total_words.lower()
##    #print (total_words)
##    
##    total=0
##    for letters in total_words:
##        total+=score[letters]
##    return total
##        




    
##    or word in words:
##        words_list.append(word)
##    return (words_list)
####    #time.sleep(5)
##    word=word.lower()
##    total=0
##    for letters in word:
##        total+=score[letters]
##    #return total
