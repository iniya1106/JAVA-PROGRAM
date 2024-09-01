import java.util.ArrayList;
import java.util.List;
public class TextJustify {
    public static void main(String[] args) {
        String[] words = {"This", "is", "an", "example", "of", "text", "justification."};
        int maxWidth = 16;
        List<String> result = fullJustify(words, maxWidth);
        for (String line : result) {
            System.out.println("\"" + line + "\"");
        }
    }
    public static List<String> fullJustify(String[] words, int maxWidth) {
        List<String> result = new ArrayList<>();
        int index = 0;
        while (index < words.length) {
            int totalChars = words[index].length();
            int last = index + 1;
            while (last < words.length) {
                if (totalChars + words[last].length() + 1 > maxWidth) break;
                totalChars += words[last].length() + 1;
                last++;
            }
            StringBuilder builder = new StringBuilder();
            int wordCount = last - index;
            int spacesToDistribute = maxWidth - totalChars;
            if (last == words.length || wordCount == 1) {
                for (int i = index; i < last; i++) {
                    builder.append(words[i]);
                    if (i < last - 1) {
                        builder.append(" ");
                    }
                }
                for (int i = builder.length(); i < maxWidth; i++) {
                    builder.append(" ");
                }
            } else {
               
                int spacesBetweenWords = spacesToDistribute / (wordCount - 1);
                int extraSpaces = spacesToDistribute % (wordCount - 1);

                for (int i = index; i < last; i++) {
                    builder.append(words[i]);
                    if (i < last - 1) {
                        for (int j = 0; j <= spacesBetweenWords + (i - index < extraSpaces ? 1 : 0); j++) {
                            builder.append(" ");
                        }
                    }
                }
            }

            result.add(builder.toString());
            index = last;
        }

        return result;
    }
}
