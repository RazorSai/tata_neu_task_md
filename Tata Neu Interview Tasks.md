**A. Descriptive Questions:**

\1. Can we nest the Scaffold widget? Why or Why not?

**Answer: Since every component in Flutter is widget, we can nest scaffolds. But it is not a good practice because, in nature, Scaffolds are meant to be use as a single component inside a single page as it loads all the basic material properties like primary colour, accent colour, etc., which are then used by the body of scaffold. Also, when we want to use tabbed interfaces like page view with bottom navigation bar, it is always good to wrap a single scaffold around the PageView widget.**




\2. What are the different ways we can create a custom widget?

**Answer:**

**First way is to create a separate file inside our projects and use Stateless or Stateful widget based on the requirements. For example, we can separate list view items by creating a custom class for list view item and accessing it inside list view builder property.**

**Second way is if we need a custom widget for a particular page, we can create a function inside the page which returns our custom widget. For example, if we want to segregate a column widget with multiple text widgets inside of it, we can create a function inside the same class which will take our required properties like text, etc., as arguments and return the text widget. This centralizes the control of text widget to one function.**




\3. How can I access platform(iOS or Android) specific code from Flutter?

**Answer: Flutter supports platform specific code (iOS or Android) using Method channels. Method channels are asynchronous and bidirectional calls, meaning users can perform other actions while method channels are executed and they can return values.  We can use method channels to access platform specific features, for example; calling camera app in Android using native Intent implementation on JAVA/Kotlin side and handling the calls using FlutterMethodChannel.**





\4. What is BuildContext? What is its importance?

**Answer: BuildContext are reference points for a widget in a widget tree. Each widget has a parent build context inside it’s build method.**



**------------------------------------------------------------------------------------------------------------------------**






**B. Coding Questions:**

\1. Refactor the code below so that the children will wrap to the next line when the display width is small for them to fit.

**Answer: We can use a widget called Wrap in this scenario. Refer the below image for example**

![](Aspose.Words.9c708d88-17dd-4f7d-bf21-f728aa266deb.001.png)

**From the above example, if we use row, we get render flex overflow error. To resolve this we use Wrap widget.**


![](Aspose.Words.9c708d88-17dd-4f7d-bf21-f728aa266deb.002.png)**By using Wrap and settings it’s property “direction” as horizontal, it will wrap the widgets to the next line as soon as the display width gets small to fit all in one line.**

\------------------------------------------------------------------------------------------------------------------------

\2. Identify the problem in the following code block and correct it.

**Answer:**

![](Aspose.Words.9c708d88-17dd-4f7d-bf21-f728aa266deb.003.png)











**In the given problem statement, it is possible for the application to get stuck in between the process since it is a very big task to be ran by the mobile application. It can cause our app to temporarily inaccessible to the user till the time the above operation is completed.**

**To counter this issue, we would put the function inside an isolate. We use the compute function and pass our LongOperationMethod along with the count for the “for” loop. This will prevent the application to be inaccessible to the end user while the operation is completed.**

**Second problem which I found was the function will only print last count. If we want to avoid this, then we have to move print statement inside the “for” loop.**

**Video for this problem statement is :- [https://drive.google.com/file/d/18i8td4qZUrP2MytS06MF-nwy7Ji8_iHU/view?usp=sharing**](https://drive.google.com/file/d/18i8td4qZUrP2MytS06MF-nwy7Ji8_iHU/view?usp=sharing)**

**-----------------------------------------------------------------------------------------------------------------------**

\3. In the below code, list1 declared with var, list2 with final and list3 with const. What is the difference between these lists? Will the last two lines compile?

**Answer:**

![](Aspose.Words.9c708d88-17dd-4f7d-bf21-f728aa266deb.004.png)










**The above problem statement can be explained with the help of the image added below**






![](Aspose.Words.9c708d88-17dd-4f7d-bf21-f728aa266deb.005.png)

**“var” keyword is used when we declare variables whose values can be changed at any given type. “final” and “const” are both the same as in their values can be assigned only once. The major difference between “final” and “const” is how the values are assigned. “final” value is assigned at runtime while “const” value is assigned at compile time. For example, lets assume “final” as a box with n number of apples. We know that there are apples, but we don’t know how much are there. After opening, we would get to know the number of apples. Whereas in “const”, we have the count of the apple, i.e, 6 apples.**


**list[2] = “Dart” will compile because we are changing the elements inside of the list, not the actual list. As you can see from the console print on the left.**

**For the last line, i.e., const list3 = list1; it will not compile since the value of list1 can change at any given time.**
