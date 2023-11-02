Creation of Chatbot in Python

• Build a command-line chatbot with ChatterBot.
• Train the chatbot to customize its responses.
• Retrain the chatbot with industry-specific data

Step 1: We need to install chatterbot module, So open Windows Power shell and run the
        following commands :
    •	python -m venv venv
    •	venv\Scripts\activate
    •	python -m pip install chatterbot==1.0.4 pytz

Step 2: Next write the following code and save it as 'bot.py' and Run the following
        command,When you run bot.py, ChatterBot might download some data and language
        models associated with the NLTK project.It’ll print some information about that
        to your console.Python won’t download this data again during subsequent runs.
     
CODE:
from chatterbot import ChatBot
from chatterbot.trainers import ListTrainer
chatbot = ChatBot("Chatpot")
exit_conditions = (":q", "quit", "exit") 
while True: 
    query = input("> ")
    if query in exit_conditions:
        break
    else:
        print(f"🪴 {chatbot.get_response(query)}")
        
Step 3: You’ll train your chatbot using ListTrainer to make it a little smarter
        from the start.You’ll also learn about built-in trainers that come with ChatterBot,
        including their limitations.

CODE:
from chatterbot import ChatBot
from chatterbot.trainers import ListTrainer
chatbot = ChatBot("Chatpot")
trainer = ListTrainer(chatbot) 
trainer.train(["Hi", "Welcome, friend     "])
trainer.train(["Are you a plant?", "No, I'm the pot below the plant!"])
exit_conditions = (":q", "quit", "exit") 
while True: 
    query = input("> ")
    if query in exit_conditions:
        break
    else:
        print(f"🪴 {chatbot.get_response(query)}")

Step 4: Repeat the 3rd Step with different Conversations. Then the chatbot will be trained
        well and successfully created using python programming language.

You can also train your Chatbot with Datasets by importing the dataset file, For example   
lets import a dataset 'chat.txt' which is an text file, the chatbot is trained by the      
dataset by using ListTrainer       

CODE:                                                                                  
#bot.py                                                                                                                                                                  
from chatterbot import ChatBot                                                        
from chatterbot.trainers import ListTrainer                                          
from cleaner import clean_corpus    
CORPUS_FILE = "chat.txt"
chatbot = ChatBot("Chatpot")
trainer = ListTrainer(chatbot) 
cleaned_corpus = clean_corpus(CORPUS_FILE)
trainer.train(cleaned_corpus)
exit_conditions = (":q", "quit", "exit") 
while True: 
    query = input("> ")
    if query in exit_conditions:
        break
    else:
        print(f"🪴 {chatbot.get_response(query)}")
                                
Dataset :  
   
hi, how are you doing?	i'm fine. how about yourself?
i'm fine. how about yourself?	i'm pretty good. thanks for asking.
i'm pretty good. thanks for asking.	no problem. so how have you been?
no problem. so how have you been?	i've been great. what about you?
i've been great. what about you?	i've been good. i'm in school right now.
i've been good. i'm in school right now.	what school do you go to?
what school do you go to?	i go to pcc.
i go to pcc.	do you like it there?
do you like it there?	it's okay. it's a really big campus.
it's okay. it's a really big campus.	good luck with school.
good luck with school.	thank you very much.
how's it going?	i'm doing well. how about you?
i'm doing well. how about you?	never better, thanks.
never better, thanks.	so how have you been lately?
so how have you been lately?	i've actually been pretty good. you?
i've actually been pretty good. you?	i'm actually in school right now.
i'm actually in school right now.	which school do you attend?
which school do you attend?	i'm attending pcc right now.
i'm attending pcc right now.	are you enjoying it there?
are you enjoying it there?	it's not bad. there are a lot of people there.
it's not bad. there are a lot of people there.	good luck with that.
good luck with that.	thanks.
how are you doing today?	i'm doing great. what about you?
i'm doing great. what about you?	i'm absolutely lovely, thank you.
i'm absolutely lovely, thank you.	everything's been good with you?
everything's been good with you?	i haven't been better. how about yourself?
i haven't been better. how about yourself?	i started school recently.
i started school recently.	where are you going to school?
where are you going to school?	i'm going to pcc.
i'm going to pcc.	how do you like it so far?
how do you like it so far?	i like it so far. my classes are pretty good right now.
i like it so far. my classes are pretty good right now.	i wish you luck.
it's an ugly day today.	i know. i think it may rain.
i know. i think it may rain.	it's the middle of summer, it shouldn't rain today.
it's the middle of summer, it shouldn't rain today.	that would be weird.
that would be weird.	yeah, especially since it's ninety degrees outside.
yeah, especially since it's ninety degrees outside.	i know, it would be horrible if it rained 
and it was hot outside.
i know, it would be horrible if it rained and it was hot outside.	yes, it would be. 
yes, it would be. 	i really wish it wasn't so hot every day. 
i really wish it wasn't so hot every day. 	me too. i can't wait until winter.
me too. i can't wait until winter.	i like winter too, but sometimes it gets too cold.
i like winter too, but sometimes it gets too cold.	i'd rather be cold than hot.
i'd rather be cold than hot.	me too.
it doesn't look very nice outside today.	you're right. i think it's going to rain later.
you're right. i think it's going to rain later.	in the middle of the summer, it shouldn't be raining.
in the middle of the summer, it shouldn't be raining.	that wouldn't seem right.
that wouldn't seem right.	considering that it's over ninety degrees outside, that would be weird.
considering that it's over ninety degrees outside, that would be weird.	exactly, it wouldn't be nice if 
it started raining. it's too hot.
exactly, it wouldn't be nice if it started raining. it's too hot.	i know, you're absolutely right.
i know, you're absolutely right.	i wish it would cool off one day.
i wish it would cool off one day.	that's how i feel, i want winter to come soon.
that's how i feel, i want winter to come soon.	i enjoy the winter, but it gets really cold sometimes.
i enjoy the winter, but it gets really cold sometimes.	i know what you mean, but i'd rather be cold than hot.
i know what you mean, but i'd rather be cold than hot.	that's exactly how i feel.
i wish it was a nicer day today.	that is true. i hope it doesn't rain.
that is true. i hope it doesn't rain.	it wouldn't rain in the middle of the summer.
it wouldn't rain in the middle of the summer.	it wouldn't seem right if it started raining right now.
it wouldn't seem right if it started raining right now.	it would be weird if it started raining in ninety degree weather.
it would be weird if it started raining in ninety degree weather.	any rain right now would be pointless.
any rain right now would be pointless.	that's right, it really would be.
that's right, it really would be.	i want it to cool down some.
i want it to cool down some.	i know what you mean, i can't wait until it's winter.
i know what you mean, i can't wait until it's winter.	winter is great. i wish it didn't get so cold sometimes though.
winter is great. i wish it didn't get so cold sometimes though.	i would rather deal with the winter than the summer.
it's such a nice day.	yes, it is.
yes, it is.	it looks like it may rain soon.
it looks like it may rain soon.	yes, and i hope that it does.
yes, and i hope that it does.	why is that?
why is that?	i really love how rain clears the air.
i really love how rain clears the air.	me too. it always smells so fresh after it rains.
me too. it always smells so fresh after it rains.	yes, but i love the night air after it rains.
yes, but i love the night air after it rains.	really? why is it?
really? why is it?	because you can see the stars perfectly.
because you can see the stars perfectly.	i really hope it rains today.
i really hope it rains today.	yeah, me too.
isn't it a nice day?	it really is.
it really is.	it seems that it may rain today.
it seems that it may rain today.	hopefully it will.
hopefully it will.	how come?
how come?	i like how clear the sky gets after it rains.
i like how clear the sky gets after it rains.	i feel the same way. it smells so good after it rains.
i feel the same way. it smells so good after it rains.	i especially love the night air when it rains.
i especially love the night air when it rains.	really? why?
really? why?	the stars look so much closer after it rains.
the stars look so much closer after it rains.	i really want it to rain today.
i really want it to rain today.	yeah, so do i.
don't you think it's nice out?	yes, i think so too.
yes, i think so too.	i think that it's going to rain.
i think that it's going to rain.	i hope that it does rain. 