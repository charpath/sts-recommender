### Modeling and Feature Development

With the Slay the Spire card data set, the features in pretty much every model are going to be the cards (because, what else would they be). However, the ways in which I use them are going to vary from model to model, and that's where my feature engineering comes in.

A lot of the work I've done on the data so far has been reorganizing all of the data into a common format, so that I could create my feature set from there. As of now, I have a DataFrame containing the state of the player's deck at every floor from 0-56 for each run in the dataset. This will allow me to create feature sets based on floors, and use different deck states at different times.

With that, I've only implemented one real model at the moment, a model that recommends the card from the choices that has the highest pickrate by the given floor. This model has some pros and some cons:
- Pros:
    - Very simple
    - Recommends cards based off of how often they're taken when they're offered, so doesn't favor rarer cards excessively
    - Still favors rare and uncommon cards, since they're generally stronger (good)
- Cons:
    - Doesn't take the current deck into account, just recommends what's the best in the most decks
    - Rare cards are almost never competing against each other until floor 16, so their pick rates will be very inflated before that
    - Still favors rare and uncommon cards, since they're generally stronger (bad)

Since a card reward is (almost always) three cards, a random model should recommend correctly 33.3% of the time. We should be able to get significantly above that with smarter models.

Even though I only have one implemented model so far, I still have plenty of ideas for other models:
- Finding which cards are the most present within decks at a certain floor (technically different from pickrate)
- A simple heuristic of always recommending rare cards over uncommons and always recommending uncommon cards over common cards
    - For this one, a list of all cards is available in the StS Discord, and I can extract card rarities from that
- Potentially even clustering cards based on which decks they're taken in, and modifying earlier models to check whether they took similar cards rather than just the same card

### Model Evaluation

Yeah so uh there's nothing here

I just didn't have enough time this week to get through everything I needed to. I had a project due on Monday and two midterms on Tuesday, I just haven't had the time to put towards this project. Maybe I'll stay up late and everything will be done by the time it gets graded, but for now just so I have something to turn in there's nothing here for now