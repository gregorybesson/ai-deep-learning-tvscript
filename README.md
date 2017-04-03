# ai-deep-learning-tvscript
A Recurrent Neural Network to create a new Simpsons tv script

## Introduction
We'll try to make an AI which will create a Simpsons tv-script. To achieve this, I'll create a Recurrent Neural Net which I'll train on many existing Simpsons scripts.
I don't wait the AI script to have any sense. But I bet on its understanding of syntax and grammar : Sentences should be well formed and be grammatically correct.

## Building and training the RNN
The steps to create this on-sense scenario are:
- Process the data. Here, we create vocab_to_int and int_to_vocab to ease the training of our RNN (using int instead of vocabs) 
and generate the result thanks to int_to_vocab
- We do tokenize punctuation (easing the training)
- We create our Word Embeddings
- We then build the RNN Cell based on LSTM (we could use Dropout to do better generalization and prevent overfitting)
- And use these cells in the RNN and add a fully connected layer
- We then batch the input and train the RNN
- With 100 epoch, batch and RNN size of 256, sequence length of 17 and a learning rate of 0.01, I've been able to achieve a train_loss = 0.199.

## Generating a TV script
My RNN has been able to understand how sentences are created and know syntax, but it's not able to create a real script as it produces non-sense:
```
homer_simpson:(reluctant) all right, i'm sorry... and you gotta do it fast?
c. _montgomery_burns:(reading)" family," we get up with no tipsy in the bar again.
homer_simpson: i can't believe it works. and everyone's got these super-tough africanized bees!
moe_szyslak:(mr) man, my dad was eh? first name yeah.
harv:(then) let's see lenny and carl doing?
moe_szyslak:(noise of agreement) well. thank you!
homer_simpson:(meaningful) don't do my family. it takes his bad.
moe_szyslak: homer, the heat's been on a stool with this time.
homer_simpson: so sad.
moe_szyslak: man, you're doin' thing as doing?
moe_szyslak: uh... well just talk about sports!
homer_simpson: let's say.? my favorite team's in it: the(raises glass in front of mouth) atlanta pants.
moe_szyslak: okay, here's the handoff.
carl_carlson: i got a little wave may a in a one. if they lose this ga--
moe_szyslak:(cutting him) it doesn't have nothin' like that out...


moe_szyslak: so lenny, who rubbed me!
moe_szyslak:(to self, happily) but i guess i feel no hero all comes all over.
moe_szyslak: listen one, moe...
lisa_simpson:" tell you... nobody gives now dance.
seymour_skinner: homer, okay? that's it got.
homer_simpson: moe, you know, who are you care for me into our song to play.
```
