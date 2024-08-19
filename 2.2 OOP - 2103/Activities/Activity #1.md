---

creation date: 2024-08-19T15:45:08
tags:
  - OOP
---

# Practice #1

```java title=practice
import java.util.*;

public class Main {
    public static void main(String[] args) {
      Helper helper = new Helper();
      Activity activity = new Activity(helper);
      
      activity.first();
      activity.second();
      activity.third();
    }
}

public class Helper {
  private Scanner scanner = new Scanner(System.in);
  
  public int scanInt(String description) {
    if (description != null) {
      System.out.print(description);
    }
    
    return this.scanner.nextInt();
  }
  
  public int sum(int[] numbers) {
    int sum = 0;
    
    for (int i = 0; i < numbers.length; i++) {
      sum += numbers[i];
    }
    
    return sum;
  }
}

public class Activity {
  private Helper helper;
  
  public Activity(Helper hlpr) {
    helper = hlpr;
  }
  
  public void first() {
    for (int i = 0; i < 10; i++) {
      System.out.println("Destin Ecarma");
    }
  }
  
  public void second() {
    int[] numbers = new int[2];
    numbers[0] = this.helper.scanInt("Enter first number: ");
    numbers[1] = this.helper.scanInt("Enter second number: ");

    int sum = this.helper.sum(numbers);

    System.out.print("Sum: " + sum);
  }
  
  public void third() {
    int size = this.helper.scanInt("Enter array size: ");
    
    int[] arr = new int[size];
    
    for (int i = 0; i < size; i++) {
      arr[i] = this.helper.scanInt("Enter a number: ");
    }
    
    for (int i = 0; i < size; i++) {
      if (arr[i] % 2 != 0) {
        continue;
      }
      
      System.out.println(arr[i]);
    }
  }
}
```
