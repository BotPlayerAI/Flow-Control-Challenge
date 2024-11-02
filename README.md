## Flow Control Challenge

```java
import java.util.Scanner;

public class Counter {
  public static void main(String[] args) {
    Scanner terminal = new Scanner(System.in);

    System.out.println("Type the first parameter");
    int firstParameter = terminal.nextInt();

    System.out.println("Type the second parameter");
    int secondParameter = terminal.nextInt();

    try {
      count(firstParameter, secondParameter);
    } catch (InvalidParametersException exception) {
      System.out.println(exception.getMessage());
    }

    terminal.close();
  }

  static void count(int firstParameter, int secondParameter) throws InvalidParametersException {
    if (firstParameter > secondParameter) {
      throw new InvalidParametersException("Second parameter need to be greater than the first parameter");
    }
    int counting = secondParameter - firstParameter;

    for (int i = 1; i <= counting; i++) {
      System.out.println("Printing the number " + i);
    }
  }
}
