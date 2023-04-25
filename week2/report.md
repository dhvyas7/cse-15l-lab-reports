Here is the code for the StringServer along with Server which we are using to create a web server:

![Code Server](serverss.png)

![Code StringServer](stringserverss.png)

The code can be run by inputting the following commands in the terminal

`javac Server.java StringServer.java`

`java StringServer 7777`

Here 7777 is a port number and can be modified to any 16-bit unsigned integer

The site can now be visited at (localhost:7777)

The numbers after the colon depend on the port number you use while calling

Now we can use this for running queries on the web server

Here's a sample showing how to use the query in a URL to add an element to the page

![Run 1](add1.png)

After this, go back to the homepage and you should see the string you just added

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

Here, we get the average as 0.0 even though we would expect 5.0 because the code we've written doesn't consider the scenario where all list elements are equal and so the sum is never incremented leading to the return value of 0



