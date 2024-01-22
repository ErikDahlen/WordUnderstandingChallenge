# Word Understanding Challenge
Word Understanding Challenge, WUC, is a benchmark for testing word understanding in LLMs.

Main focus of this benchmark is to test if a model can understand simple words, like nouns, adjectives, and verbs. The goal of this test is to ensure that models understand what they are saying, and without understanding simple words, it is unlikely the model will understand more complex tasks and queries.

#Exempel of query:
Hi, let's play a game where you should guess which out of 4 words does not belong. Provide an explanation of why afterwards. Here are the words: apple, red, green, and banana.

The four words will be replaced by different words each time. The combination can either be made manually to test specific combinations or randomly to test unlikely combinations.

#Stregth of the test:
WUC is a very simple test, and still a test that might be hard for LLMs to answer correctly if they don't understand the full meaning of the word. With different combinations different nuances are important, which makes this a great test for word understanding.

A very strong argument for WUC is that it is practically impossible for an LLM to memorize all combinations during training. If we have a rough estimate of 100´000 words which are nouns, adjectives, and verbs the total number of combinations will be huge. If we assume that the order of the words does not matter, it will be in the order of magnitude of 10^19 different combinations. Even if you manage to compress each combination into only 1 byte of data, you would need 10 millions 1 TB harddrives to store all the combinations on.

The benefit of WUC is also that the number of combinations are so high, so the model cannot memorize even a small fraction of the combinations. The positive side of this is that we only need to test a fairly small number of cases, maybe 100 different combinations, before it becomes extremely unlikely that we would by chance happen to choose only combinations that have been memorized by the model.

#Test setup:
There are three different scores for the model, correct, tie, and fail. Correct is if it answers the only correct answer, tie is if it answers one out of many correct answers, and fail is every answer that is wrong or doesn't make sense.

1. Pick a model to test, and document it.
3. Generate 50 combinations manually with words chosen.
4. Generate 50 random new combinations of the same words.
5. Go over the 100 combinations and determine the correct answers.
6. Ask the model for its answer for each of the 100 combinations.
7. Document all the answers, and give the model a score.
8. Upload the model information, words, combinations, answers, and score to this repo.

Important key things to keep an eye open for:
1. If the model gives an answer you think makes sense but missed before, add that as a tie.
2. A correct score is 2 points, a tie is 1 point and a fail is 0 points.
3. The total score of the model will be something like 120/150. (If all combinations only have one correct answer the maximum score is 200 and if all combinations are tied it is 100, in most cases the maximum is somewhere between.)
