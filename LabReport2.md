# Lab Report 2: Servers and Bugs

In this report, we will be writing a web server called `StringServer` that supports the behavior of keeping track of a single string that get added to. We will also discuss the methods used to create the web server, the relevant arguments to those methods, and the values of any relevant fields of the class. 

Then, we will go over inputs for a buggy program, describing the outputs and tests of failure-inducing inputs and inputs that don't induce a failure. We will then describe the symptoms of running those two inputs and identify the bug within the program in order to fix and address the issue.

## Part 1: StringServer Web Server

Below is the code for `StringServer`:

```
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> stringList = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            //open the web server with a welcome message
            return String.format("Welcome to StringServer");
        } else if (url.getPath().equals("/showtext")) {
            return String.format("Hello World");
        } else {
            System.out.println("Path: " + url.getPath());
            //if the path contains "/add-message", the argument (message) after the
            //query is stored in an ArrayList and is displayed on the web server
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("s=");
                stringList.add(parameters[1]);
                //after inputing a new argument
                //the message is displayed on the next line
                return String.join("\n", stringList);
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
Here are two screenshots of the web server using the request `/add-message?s=<string>`.

<img width="500" alt="Screen Shot 2023-01-25 at 7 02 35 PM" src="https://user-images.githubusercontent.com/122497165/214749856-8a93e728-9db1-44e3-b8bc-ecd01c67a783.png"> 

**Screenshot 1**

* In Screenshot 1, the method that is being called in the code is the `public String handleRequest(URI url)`.
* The relevant arguments to the method is the `URI` or the **Uniform Resource Identifier** which contains a uniqe sequence of characters needed to identify a resources by web technologies. The `url` contains the elements needed to find the `StringServer`(ex. `url = http://localhost:4127`), which includes the Protocool and path of the web server. Within the code, the method takes in the url and checks to see what is contained in the path. If the path contains a certain substring (ex. `/add-message`), it will display a String that was input after the path (ex. `/add-messaage?s=<String>`). After the query, `s=`, it is read in as a string, and the string is stored into a String array called parameter. The method takes in the url, reads its path, and displays the second parameter (String) onto the web server. The second parameter is also stored into a String ArrayList called listString, which the web server stores strings that are read in everytime the url path changes with a new request.
* From the specific request of `/add-message`, the String ArrayList is updated as the second parameter that is read in of the path is always stored into the ArrayList. The String array is always being updated as well as the path is seperated into individual strings that are stored into the array. The first "parameter" of the array is the query `s=` and the second "parameter" would be the string being requested to display onto the web server. 

<img width="500" alt="Screen Shot 2023-01-25 at 7 08 18 PM" src="https://user-images.githubusercontent.com/122497165/214750266-4b945215-8e95-478b-9b00-a08c20fcdbe1.png">

**Screenshot 2**

* In Screenshot 2, the `public String handleRequest(URI url)` is also being called.
* The relevant arguments to the method is the same ones taken the first time the web server request was done as performing a request with a different string performs the same method as it reads through the path. If it contains a specific substring, the method will return a formatted String of message which will then be displayed onto the web server
* Since `/add-message` is used again in the second screenshot, the values of the relevant fields of the class are updated. Every time a request is made, the method is called, where the path is read in and the String array is updated and used to read in each invidual string of the path. With the second string or "parameter" of the array, it is stored into the listString ArrayList. In the first screenshot, the request first included the message `Hello! Welcome to CSE15L` as it is the first string stored into the ArrayList. In the second screenshot, another request is made with the messaage `Hello! I am in CSE 15L` with the first message being displayed on top. This is because the method updated the ArrayList with another string, displaying the contents of the ArrayList on the same web server.

## Part 2: Bugs in Array Methods

In a file called `ArrayExamples.java`, it contained some buggy programs as the given methods were not working as intended. One method in the file that has a bug is the `static int[] reversed(int[] arr)` as shown below:
```
public class ArrayExamples {
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
The method is intended to return a new array with all the elements of the input array in reversed order. When using JUnit test in the tester file `ArrayTests.java`, the method passes certain cases, but doesn't pass for other cases. In this situation, we had to debug and identify where in the program is causing the wrong output. First, the failure-inducing input for the program was tested as shown below: 

```
@Test
  public void testReversed2() {
    int[] input2 = {1, 2, 3, 4 ,5};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{5, 4, 3 ,2, 1}, input2);
  }
```
One input that doesn't induce a failure was with an empty list, shown below. We tested this case by reversing the array and checking to see if the array matched the expected array thats empty. The test passed, indicating that the method `reversed(int[] arr)` works, which in reality, it does not.

```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

To see the symptoms of running the buggy program, we tested the failure-inducing case, where we created an int array that contained the ints `{1, 2, 3, 4, 5}`. We then reversed the array and tested to see if the array would match the expected array, which is a new array of the original elements but in reversed order (`{5, 4, 3, 2, 1}`). As a result, the test failed and was given an error saying that the expected element at index 0 was `5` but was actually `0`. 

<img width="500" alt="Screen Shot 2023-01-25 at 8 53 43 PM" src="https://user-images.githubusercontent.com/122497165/214761245-a72d116f-9dfe-4896-a77f-861235c181dc.png">

We tested the method with the input that doesn't induce a failure and successfully passed as the empty input array matched the expected, reversed input array:

<img width="500" alt="Screen Shot 2023-01-25 at 9 08 49 PM" src="https://user-images.githubusercontent.com/122497165/214762772-46917796-fcef-4d0d-b327-ea7a8d5d1edf.png">

Based on the failure-inducing test, we were able to look through the method and debug the parts that were needed to be corrected in order to work for all cases. 

Here is the method before the change:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
Here is the method after the change:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
After making the change to the method, the failure-inducing test was finally able to pass. When looking carefully through the method, we found that it was assigning elements to the wrong array. In the original method, a new Array was created with the original length. To store the original elements in reverse order into a new array, the method had to traverse the original array from the end, however, the bug was that the method was traversing the elements of the new Array and inputting them into the original array in reverse order. This caused the method to return the original Array with the elements all being 0 since the new Array elements were being assigned to original array. The fix for this method was within the for loop, where we had to get the indexes of the original array, instead of the new one, in reverse order and assign them into the new Array. We would then return the new Array instead of the original.

## Part 3: Takeaway

Through learning and engaging in the lab tasks of Week 2 and 3, I was able to takeaway many new skills and methods used within programs, files, and web servers. One thing that I learned from lab in Week 2 was setting up GitHub Desktop and utilizing its features to download code from my own repository and upload changes. I was able to clone my lab reports repository and track and record changes. From this lab task, I was able to learn how utilizing Github Desktop can help with collaboration on projects and development workflow. 
