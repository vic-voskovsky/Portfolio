
[preface]

    Hello, and thank you for taking the time to read my analysis of this snippet of League of Legends data. 
    This dataset came my way from Kaggle, while I was looking for a random dataset to run a model on. 
    I hope to be able to predict the outcome of a game based on some given statistics and possibly extract further 
    information from this numerical dataset. 

[introduction]

    "League of Legends is a multiplayer online battle arena video game developed and published by Riot Games for Microsoft Windows and macOS. 
    Inspired by the Warcraft III: The Frozen Throne mod Defense of the Ancients, the game follows a freemium model and is supported by microtransactions." 
        https://en.wikipedia.org/wiki/League_of_Legends

[League of Legends: Created by Riot Games.]
    League of Legends (LoL) takes place in a generic timeline where individuals can choose from 134 champions, each consisting of a plathora of unique abilities. 
        On top of the character unique ability combinations, each player can choose from 43,740 possible rune tree combinations which are unique to the Player also.
        Source: https://www.reddit.com/r/leagueoflegends/comments/7c7ahk/there_are_4374087480_different_possible/
            Furthermore, each player can choose two summoner spells for a given game. 
            As you can see the amount of possible combination that a player will go into a game with is immense, and this is what peaks my interest in this subject. 
[data]
    In this specific data set we do not know the players champions, skills, rune tree combinations or summoner spells. This is good, because its giving us a random 
    probability for a given matchup. In LoL, we have two teams of 5 players facing eachother on a slightly off balanced, two sided map. The reason I am saying unbalanced
    is because of a statistical Blue Side Advantage. In short teams which get randomly selected to play on the blue side of the map tend to win by 2-4%, and the weird 
    part is that Riot Games has tried to fix this for years! Over the 10+ years that League of Legends has been around, this advantage has been a plague on the game, 
    because it is prevelent in both low-skill and high pro-level games. (Similarity between baseball "park factors")

    But i would point out that this effect has been mostly mitigated as 
    much as possible by Riot Games, it would have only a marginal impact on the dataset, especially this late in the games development. The fact is that there is an 
    advantage in camera positions in League of Legends for the blue side, the way the camera is position allows blue side player greater sight over the top of their screen
    because they attack from the bottom, the analysis is not as interesting as the conclusion but please refer to the link below to learn more.  
        Here: https://www.unrankedsmurfs.com/blog/lol-blue-side-advantage. 
        To learn more about how the game is played head to >>> https://na.leagueoflegends.com/en-us/how-to-play/

[problem]
    Do you think it would be possible to predict the outcome of a game lasting on average 30-60 minutes, byt taking a statistical snapshot of both teams at the 
    10 minute mark? 

    [hypothesis]
    Using the data given at 10 minutes can we predict the outcome of a full game with a "Simple" logistic model. 

[exploration]
    - The data provided had 38 feature columns, split between both teams, so 19 for blue and 19 for red. 
    - 2 of these columns were potentially negative integers, and those were Gold and Experience points differences. 
    - It looks like Total Gold and Total Experience points could potentially be good indicators of a win or loss. 
    - I decided to use the following primary feature vectors in my Logistic Regression model:
        Total Gold and Total Experience @ 10 minutes. 
    - For my target variable, I used a binary column of 0 or 1 for blue win or loss. 

[model]
    - I ended up using the logistic regression model, since I wanted to predict a binary value between 0 and 1. 
    - Sensitivity score: 0.7265% (out of blue wins)
    - Specificity score: 0.7164% (out of blue losses)

[evaluation]
    - I assume that my model does a good job predicting the outcome of the game around 70% of the time. 

[answer] 
    I dont think I am ready to use this model in production, since I don't believe that a 70% score would be good 
    enough to accept my original hypothesis. But I dont reject my hypothesis, that I Cannot do this with more time and or data. 



