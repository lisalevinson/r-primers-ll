# programming basics

## 01-functions

https://vimeo.com/220490105

Most functions produce a result like we see here, but some functions are designed to trigger side effects in the background.

00:07
As a new R user you should know how to do three things with a function. First, you should know that if you type the name of a function by itself, R will return the code that is stored in the function.

00:13
This is the code that R runs when you call the function. The code may not mean anything to you now, but it can be useful down the road.

00:25
Second, you should know that to run a function you must do more than type its name. You must place a pair of parentheses behind the function name.

00:33
If the function requires any input to do its job you place the input between the parentheses, like the number three here.

00:42
Finally, you should know that if you put a question mark in front of the function name and click run, R will open a help page for the function.

00:49
This is the best way to learn about how the function works. Notice that you do not include parentheses when you open a help page.

00:57

## 02 - arguments

https://vimeo.com/220490157

Here we see that the log function recognizes two arguments, one named x and one named base. You can use these names to look up what the arguments do, for example in log's help page.

00:20
You can also use names when you call log to ensure that the right input is matched to the right argument.

00:33
If you don't use argument names R will match your inputs to arguments in the order that they appear. This can sometimes cause problems, for example if you get your inputs out of order.

00:40
In practice most R users specify argument names for every input after the first one or two inputs. Before you move on I'd like you to notice one more thing about arguments. Some arguments are optional.

00:54
For example, notice that the base argument of log comes with a default value. This means that base is an optional argument.

01:09
R will use your value for base if you supply one, otherwise R will use the default value which here is exponent of one: Euler's number.

01:17
In contrast, x is a required argument because it does not come with a default value. If you do not supply an x argument the log function will fail.

01:28


## 3-objects (03-geometric objects)

https://player.vimeo.com/video/223812632

Transcript

So far we've been happy to run functions and then read the results on the screen. If you'd like to use those results later you'll need to save them.

00:00
In R you save results by creating an object. To create an object type a name for the object and then use the assignment operator to store a value in the object.

00:08
The operator is a less than sign followed by a minus sign. The result looks like an arrow which is a helpful visual mnemonic.

00:18
R will store whatever appears on the right of the arrow into the object that appears on the left. You can save individual values or you can directly save the results of a function.

00:26
Whenever you call an object R will replace the object with the value assigned to the object when R executes the code.

00:38
This makes it easy to pass results to new functions or to see the contents of an object. To do that just call the object name by itself.

00:45
If you assign a value to an object that already exists R won't hesitate to overwrite the old value. So be careful when you choose your object names.

## 04-vectors

https://vimeo.com/220490316

R stores every value as a vector, which is a one dimensional array of values. When you create a single value in R, R sees the value as a vector of length one.

00:00
When you run this rnorm call, R sees the result as a vector of length ten. You can create your own vectors with the c function which combines the values into a single vector.

00:10
If you want to, you can assign each value a name as you do so. Creating your own vectors is a very useful thing to do because many R functions expect a vector.

00:22
For example, mean computes the mean of a vector of values, and sum computes the sum. Vectors also help you work efficiently. You can give many R functions a vector of input.

00:33
R will apply the function separately to each element in the vector and return the result as a new vector.

00:48
If you use multiple vectors of input R will apply the function to the first element of each vector, and then to the second element of each vector,

00:54
and so on until R reaches the end of the vector.

01:02

## 05 types

https://vimeo.com/220490241
R recognizes different types of vectors based on clues in your values. For example, if your values are all numbers, R knows that the vector is numeric and R can do math with it.

If your values are surrounded by quotation marks, R knows that the vector contains character strings and R can do things like count the number of characters in each string.

By recognizing what type of data you're using, R can behave more intuitively. Altogether R recognizes six different types of data.

You can check the type of a vector with typeof. Numeric vectors contain numbers and possibly decimal points and negative signs.

They have the type double which is a computer science term that R associates with decimal numbers. Character vectors contain values surrounded by quotation marks.

00:39
Integer vectors contain integers followed by a capital L. Logical vectors contain only TRUEs and FALSEs written in all capital letters.

00:50
R also recognizes complex vectors and raw vectors, but we won't cover these because you are unlikely to encounter them while doing data science.

01:02
It is helpful to know that each vector in R can only contain one type of data. If you try to combine types within a single vector R will collapse everything to the same type, often a character vector.

01:12
If you want to save different types of values in the same object you will need to use a list, which is a data structure that we'll look at in the next video.

01:25
Later you'll learn about other classes of data that are built on top of R's basic types. R developers have come up with ingenious ways to use the six basic types to represent other classes of data like dates and times, and factors.

01:33
But for now, it's important to realize that every value in R is based on a double, character, integer, logical, complex, or raw vector.

## 06-lists

https://vimeo.com/220490360

In addition to vectors, R comes with a second very useful data structure: the list. A list is like a vector of vectors. Each element in the list can be a separate vector or even another list.

00:00
For example, this list contains three elements. The first element is a numerical vector length five. The second is a character vector of length one,

00:12
and the third element is a logical vector of length one. This list illustrates a useful feature of lists. You can store different types of data in the same list because each element of the list is its own vector with its own type.

00:22
Recall that basic vectors can only store a single type of data. You can make lists like this with the list function.

00:35
List works like the c function. Give list the elements of the list to make, separated by commas. If you like you can assign names to the elements as you go (which I recommend).

00:43
If you assign names to each element of the list you can access the contents of the elements by typing the name of the list followed by a dollar sign, followed by the name of the element.

00:56
Lists are essential to data science because R uses a specific type of list to store tabular data, and that's the data frame.

01:07
R displays data frames (like the iris data frame here) as a table. But R saves data frames as a list. Each column of the data frame is a vector that is saved as an element of the list.

01:15
For example we can see how R saves iris. Iris is actually a list of five vectors. The names of the columns in iris are the names of the elements in the list.

01:28

## 07-packages

https://vimeo.com/220490447


R contains tens of thousands of functions, objects, and help pages. To save memory, R does not load every function, or object, or help page every time you start R.

00:00
Instead, R loads only a core set of functions and objects, known as Base R. Other functions and objects are stored in collections known as packages.

When you want to use these functions you must first load the package they come in with the library function.

00:21
For example, the ggplot function comes in the ggplot2 package. If I try to use ggplot before I load the ggplot2 package, R returns an error message: could not find function ggplot.

00:27
Once I load the ggplot2 package, R can find the ggplot function and I can begin using it. If you're using R locally on your computer you must download each package that you want to use (just as you need to download R).

00:42
You can use R to download the packages by running install.packages at the command line. Give install.packages the names of the packages that you wish to download as a character vector and R will take care of the rest.

00:56
R downloads and installs the packages for you. You don't need to worry about installing packages in these tutorials. We've already installed everything you'll need.

01:10
In most cases we've also already loaded the packages that you will use with library. Still, it is important to understand how R's package system works.

01:20

# dataviz 

## 01-histograms

https://vimeo.com/221607341

A histogram divides a continuous axis into equal length intervals known as bins. It then counts the number of observations that appear in each bin and displays the results as a bar that spans the width of the bin.

00:20
So for example here in our first bin there are three observations, so the histogram would plot a bar the width of the bin that has a height of three.

00:33
The next bin has eight observations, and then the next bin has ten observations, and so on. The height of each bar is mapped to the number of observations in the bin, which makes our histogram.

00:40
The width of the bins is known as the binwidth which is an important number in histograms. If we change the binwidth of our histogram and then repeat our process the histogram will look different.

00:52
Now we have more bins and they each have different heights. However this is the same distribution and the same data.

01:05
As a result it's important to experiment with different binwidths when you create a histogram. Different bin widths can reveal different patterns within the same data.

01:14

# tidy data

## 02 wide-to-long
https://vimeo.com/229581247

no transcript - gather

## 03-long-to-wide
https://vimeo.com/229581273 

no transcript - spread??


