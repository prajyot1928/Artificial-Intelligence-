# CODE 
import java.util.*;
public class SentimentAnalysis {
    public static void main(String[] args) {
        String[] sentences = {
            "I love this movie!",
            "This movie is terrible."
        };
        for (String sentence : sentences) {
            boolean isPositive = isPositiveSentiment(sentence);

            if (isPositive) {
                System.out.println("\"" + sentence + "\" is positive.");
            } else {
                System.out.println("\"" + sentence + "\" is negative.");
            }
        }
    }

    public static boolean isPositiveSentiment(String sentence) {
        Set<String> positiveWords = new HashSet<>(Arrays.asList("love", "great", "awesome", "wonderful"));
        Set<String> negativeWords = new HashSet<>(Arrays.asList("hate", "terrible", "bad", "awful"));
        int positiveCount = 0;
        int negativeCount = 0;
        String[] words = sentence.split("\\s+");
        for (String word : words) {
            if (positiveWords.contains(word.toLowerCase())) {
                positiveCount++;
            } else if (negativeWords.contains(word.toLowerCase())) {
                negativeCount++;
            }
        }
        return positiveCount > negativeCount;
    }
}

# OUTPUT:

# "I love this movie!" is positive.
# "This movie is terrible." is negative.




