# AI-BASED-RECOMMENDATION-SYSTEM

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : G DEEPIKA

*INTERN ID*: CT6WQZA

*DOMAIN*: JAVA PROGRAMMING

*DURATION* : 6 WEEKS

*MENTOR*: NEELA SANTHOSH


*DESCRIPTION*:
Data Loading:

FileDataModel model = new FileDataModel(new File("user_preferences.csv"));
This line reads user preference data from a CSV file named "user_preferences.csv". The file should contain user IDs, item IDs, and preference values (e.g., ratings). Mahout's FileDataModel parses this data into a format the recommendation engine can use.
Similarity Calculation:

PearsonCorrelationSimilarity similarity = new PearsonCorrelationSimilarity(model);
This creates a PearsonCorrelationSimilarity object. This object calculates the similarity between users based on their preference data. Pearson correlation is a statistical measure of how closely related two sets of data are. In this case, it determines how similar users are in their preferences.
Neighborhood Selection:

NearestNUserNeighborhood neighborhood = new NearestNUserNeighborhood(2, similarity, model);
This creates a NearestNUserNeighborhood object. This object selects the N (in this case, 2) most similar users to a given user. These similar users form the "neighborhood" used for recommendations.
Recommender Creation:

Recommender recommender = new GenericUserBasedRecommender(model, neighborhood, similarity);
This creates a GenericUserBasedRecommender object. This is the core of the recommendation engine. It uses the data model, similarity metric, and neighborhood to generate recommendations. User based recommendations find users similar to the target user, and recommend items that those similar users liked.
Recommendation Generation:

List<RecommendedItem> recommendations = recommender.recommend(1, 3);
This line generates recommendations for user ID 1. It asks for the top 3 recommended items. The recommender.recommend() method returns a list of RecommendedItem objects, each containing an item ID and a predicted preference value.

*Output*:
1,101,5.0
1,102,3.0
1,103,2.5
2,101,2.0
2,102,2.5
2,103,4.0
2,104,5.0
3,101,3.0
3,104,4.5
3,105,5.0
4,102,3.0
4,103,4.0
4,105,2.0
5,101,4.0
5,102,3.0
5,103,1.0
5,104,1.0
