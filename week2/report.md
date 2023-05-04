Here is the code for the StringServer which we are creating:

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> library = new ArrayList<String>();

    public String handleRequest(URI url) {

        if (url.getPath().equals("/")) {
            return toString(library);

        } else if (url.getPath().contains("/add-message")) {

            String[] parameters = url.getQuery().split("=");

            if (parameters[0].equals("s")) {
                library.add(parameters[1]);

                return toString(library);
            }

        }

        return "404 Not Found!";
            
    }

    public static String toString(ArrayList<String> library) {
        String listStrings = "";

        for(int i = 0; i < library.size(); i++) {
            listStrings += library.get(i) + "\n";
        }
        return listStrings;
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
The code can be run by inputting the following commands in the terminal

`javac Server.java StringServer.java`

`java StringServer 7777`

Here 7777 is a port number and can be modified to any 16-bit unsigned integer

The site can now be visited at (localhost:7777)

The numbers after the colon depend on the port number you use while calling

Now we can use this for running queries on the web server

Here's a sample showing how to use the query in a URL to add an element to the page

![Run 1](add1.png)

After this, you should see the string you just added on refreshing the webpage

![Output 1](op1.png)


Part 2:

```
@Test
 public void testAverage(){
    double[] input1 = {5,5,5,5,5};
    assertEquals(5.0, averageWithoutLowest(input1));
  }
@Test
  public void testAverage2() {
    double[] input1 = {1,2,3};
    assertEquals(2.5, averageWithoutLowest(input1));
  }
```

Here, we get the average as 0.0 even though we would expect 5.0 because the code we've written doesn't consider the scenario where all list elements are equal and so the sum is never incremented leading to the return value of 0.

For testAverage2, we get the correct expected value of 2.5

Here are the test results
![JUnit Test](junittests.png)

The original code is as follows:

```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```


The fix for the code is as follows:


```
static double averageWithoutLowest(double[] arr) 
  {
    double sum=0;
    double lowest=arr[0];
    int c=0;
    if (arr.length==1||arr.length==0)return 0;
    for(double i:arr)
    {
    	if(i==lowest)c++;
    	else if(i<lowest)lowest=i;
    }
    if(c==arr.length)return lowest;
    for(double i:arr)
    {
    	if(i>lowest)sum+=i;
    }
    return sum/(arr.length-1);
  }
```


Part 3:


I learned how to set up a web server and create queries. I also learned how to write functionalities like adding a query, removing a query and replacing a query.
