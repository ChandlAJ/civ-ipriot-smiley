# Evidence and Knowledge

This document includes instructions and knowledge questions that must be completed to receive a *Competent* grade on this portfolio task.

## 1. Required evidence

### 1.1. Answer all questions in this document

- Each answer should be complete, well-articulated, and within the specified word count limits (if added) for each question.
- Please make sure **all** external sources are properly cited.
- You must **use your own words**. Please include your full chat transcripts if you use generative AI in any way.
- Generative AI hallucinates, is not an authoritative source

### 1.2. Make all the required modifications to the code

- Please follow the instructions in this document to make the changes needed to the code.

- When requested to upload evidence, upload all screenshots to `screenshots/` and embed them in this document. For example:

```markdown
![Example Running Code](screenshots/screenshot1.png)
```

![Sample](screenshots/sample.png)
> Note the `!`, and the use of a relative path.

- You must upload the code into your GitHub repository.
- While you can use a branch, your code should be in main when you submit.
- Upload a zip of this repository to Blackboard when you are ready to submit.
- You will be notified of your result via Blackboard
- However, if using GitHub classrooms, you may also receive additional feedback on GitHub directly

### 1.3. Optional: Use of Raspberry Pi and SenseHat

Raspberry Pi or SenseHat is **optional** for this activity. You can use the included `sense_hat.py` file to simulate the SenseHat on your computer.

If you use a Pi, please **delete** the `sense_hat.py` file.

### 1.4. Accessible version of the code

This project relies on visual patterns that appear on an LED matrix. If you have any accessibility requirements, you can use the `udl/accessible` branch to complete the project. This branch provides an accessible code version that uses text-based patterns instead of visual ones.

Please discuss this with your lecturer before using that branch.

## 2. Specific Tasks & Questions

Address the following tasks and questions based on the code provided in this repository.

### 2.1. Set up the project locally

1. Fork this repository (if not using GitHub Classrooms)
2. Clone your repository locally
3. Run the project locally by executing the `main.py` file
4. Evidence this by providing screenshots of the project directory structure and the output of the `main.py` file

![Local Execution screenshots](screenshots/2.1_screenshot_project_directory.png)
![Local Execution screenshots](screenshots/2.1_screenshot_output_mainpy.png)

If you are running on a Raspberry Pi, you can use the following command to run the project and then screenshot the result:

```bash
ls
python3 main.py
```

### 2.2. Fundamental code comprehension

 Answer each of the following questions **as they relate to that code** supplied by in this repository (ignore `sense_hat.py`):

1. Examine the code for the `smiley.py` file and provide  an example of a variable of each of the following types and their corresponding values (`_` should be replaced with the appropriate values):

   | Type                    | name        | value                              |
   | ----------              |-------------|------------------------------------|
   | built-in primitive type | int         | 255 (used in colours list)         |
   | built-in composite type | WHITE       | (255, 255, 255)                    |
   | user-defined type       | dim_display | self.sense_hat.low_light = dimmed  |

2. Fill in (`_`) the following table based on the code in `smiley.py`:

   | Object                   | Type   |
   | ------------             |--------|
   | self.pixels              | list   |
   | A member of self.pixels  | tuple  |
   | self                     | Smiley |

3. Examine the code for `smiley.py`, `sad.py`, and `happy.py`. Give an example of each of the following control structures using an example from **each** of these files. Include the first line and the line range:

   | Control Flow | File     | First line | Line range |
   | ------------ |----------|------------|------------|
   |  sequence    | happy.py | 39         | 39 - 43    |
   |  selection   | happy.py | 31         | 31         |
   |  iteration   | sad.py   | 25         | 25 - 30    |

4. Though everything in Python is an object, it is sometimes said to have four "primitive" types. Examining the three files `smiley.py`, `sad.py`, and `happy.py`, identify which of the following types are used in any of these files, and give an example of each (use an example from the code, if applicable, otherwise provide an example of your own):

   | Type                    | Used? | Example                                                          |
   | ----------------------- |-------|------------------------------------------------------------------|
   | int                     | yes   | used within lists in the happy.py file for mouth and eyes        |
   | float                   | yes   | used in happy.py file for delay parameter in blink method (0.25) |
   | str                     | no    | EXAMPLE: greeting = "Hello and welcome"                          |
   | bool                    | yes   | wide_open parameter used in both sad.py and happy.py files       |

5. Examining `smiley.py`, provide an example of a class variable and an instance variable (attribute). Explain **why** one is defined as a class variable and the other as an instance variable.

> YELLOW is an example of a class variable as it's value is remains consistent for all instances of a smiley. Conversely, the self.pixels variable is an instance variable as it is defined within the "__init__" method and
> it's value can vary with each instance and based on the object it references (self).
>

6. Examine `happy.py`, and identify the constructor (initializer) for the `Happy` class:
   1. What is the purpose of a constructor (in general) and this one (in particular)?

   > The constructor in the happy.py file is the "def __init__(self):"
   > The purpose of a constructor is to assign attributes to an object when it is created, to reduce manual input and mitigate the risk of errors. 
   > In the constructor within the happy.py file, it serves the purpose of ensuring the base smiley is created with the correct pixel layout for the eyes and mouth.
   >

   2. What statement(s) does it execute (consider the `super` call), and what is the result?

   > The super() method will ensure that all the Smiley class attributes are applied before the changes within the Happy constructor are run. 
   > Following this, the self.draw_mouth and self.draw_eyes will change the relevant pixels to black to reflect the happy smiley, thus creating the appearance of a happy face.
   >

### 2.3. Code style

1. What code style is used in the code? Is it likely to be the same as the code style used in the SenseHat? Give to reasons as to why/why not:

> The code utilises the PEP8 style. It is likely that the same code style is applied in the SenseHat as it is the widely accepted and followed style for Python code that is widely adopted.
>

2. List three aspects of this convention you see applied in the code.

> Indentation: the code has been written adhering to the PEP8 convention for indentation by utilising 4 spaces.
> Comments: The code includes clear comments in a sentence structure, and where applicable docstrings have also been included when defining functions.
> Naming conventions: the appropriate naming conventions according to the PEP8 guidelines have been used throughout the code, with classes using Camel case and all functions and variables being in snake case.

3. Give two examples of organizational documentation in the code.

> A Docstring is used at the top of the main.py file to describe the purpose of the main program as well as providing additional information in relation to the use of SenseHat for its functions.
> A comment has been included within the '__init__' of the Smiley classed capturing the fact that the SenseHat object has been encapsulated.
>

### 2.4. Identifying and understanding classes

> Note: Ignore the `sense_hat.py` file when answering the questions below

1. List all the classes you identified in the project. Indicate which classes are base classes and which are subclasses. For subclasses, identify all direct base classes.
  
  Use the following table for your answers:

| Class Name | Super or Sub? | Direct parent(s) |
|------------|---------------|------------------|
| Smiley     | Super         | nil              |
| Happy      | Subclass...   | Smiley           |
| Sad        | Subclass...   | Smiley           |
| Blinkable  | Subclass...   | Happy            |

2. Explain the concept of abstraction, giving an example from the project (note "implementing an ABC" is **not** in itself an example of abstraction). (Max 150 words)

> Abstraction allows certain features and complexity of a class to be hidden from areas of code to create a clean and maintainable code within the program, in this case the blinkable.py file contains an abstract method for the blink function within the class.
>

3. What is the name of the process of deriving from base classes? What is its purpose in this project? (Max 150 words)

> Inheritance, in this project inheritance is used to ensure the initial set up of the base for a smiley is initialised before making alterations to display the specific look of the happy and sad classes. 
> This means these attributes only need to be declared once at the parent class level, creating efficiency in the code.
>

### 2.5. Compare and contrast classes

Compare and contrast the classes Happy and Sad.

1. What is the key difference between the two classes?
   > The ket difference in the Happy and Sad classes is that the Happy class inherits from two parent classes, "Smiley" and "Blinkable" and as such by default has the additional attributes as the Sad class is only inheriting from "Smiley".
   >
2. What are the key similarities?
   > Both the Happy and Sad classes inherit the attributes of the "Smiley" class and include functions to alter the pixel colours of the smiley to draw a mouth and eyes that are reflect the 'mood' that the class is representative of.
   >
3. What difference stands out the most to you and why?
   > The definition of the blink function being present in the Happy class but not in the Sad class is the point of difference that most stands out. 
   > It is evident that there is additional functionality built within the Happy class that provides more interactivity through the calling of methods.
   >
4. How does this difference affect the functionality of these classes
   > The inclusion of the blink function in the Happy class allows for the blink method to be called on an instance of the class. 
   > That is, a smiley within the Happy class has the ability to blink, whereas those within the Sad class do not, given that the blink function is not declared.
   >

### 2.6. Where is the Sense(Hat) in the code?

1. Which class(es) utilize the functionality of the SenseHat?
   > The Smiley class directly imports the functionality of SenseHat and therefore can use it. 
   > Additionally, both the Happy and Sad classes can utilise SenseHat functionality through inheritance from the parent class Smiley, although they do not directly import it. 
   >
2. Which of these classes directly interact with the SenseHat functionalities?
   > The Smiley class is the only class that can directly interact with the SenseHat functionality as it is the only one in which SenseHat is imported into.
   >
3. Discuss the hiding of the SenseHAT in terms of encapsulation (100-200 Words)
   > Encapsulation has been used to hide the functionality of SenseHat within the Sad and Happy classes in that it is inherited from the parent Smiley class. Both classes can perform functions by calling those of the parent class however there is no written SenseHat code in either.
   > Additionally, the base code of the SenseHat is hidden and encapsulated even at the parent class (Smiley) level as it has been defined as its own class and then imported into the Smiley class. 
   > This means that the base code of SenseHat cannot be altered from within any of the smiley classes and is protected in this way through its encapsulation.
   >

### 2.7. Sad Smileys Can’t Blink (Or Can They?)

Unlike the `Happy` smiley, the current implementation of the `Sad` smiley does not possess the ability to blink. Let's first explore how blinking has been implemented in the Happy Smiley by examining the blink() method, which takes one argument that determines the duration of the blink.

**Understanding Blink Mechanism:**

1. Does the code's author believe that every `Smiley` should be able to blink? Explain.

> No, the author of the code believes that only Happy smileys should be able to blink. If it was a behaviour that is to be expected of all smileys, it would be defined within the parent class (Smiley) however this is not the case and in fact is only defined in the Happy class.
>

2. For those smileys that blink, does the author expect them to blink in the same way? Explain.

> Yes, it appears that the author believes all smileys should blink the same, this can be determined by the fact that the parameters for the blink function, and specifically the delay has been set and does not reference a variable that can be altered from one instance to another.
>

3. Referring to the implementation of blink in the Happy and Sad Smiley classes, give a brief explanation of what polymorphism is.

> Polymorphism enables different classes to have methods with a shared name that initiate different behaviours from one another. In reference to the blink function, Polymorphism can be used to enable the blink function to elicit differing behaviours within the smiley, this means that the way a happy smiley blinks can look different to how a sad smiley blinks.
>

4. How is inheritance used in the blink method, and why is it important for polymorphism?

> Inheritance is used in the blink method by the fact that it is set as a parent class for the Happy class. This means that the structure of the Happy smiley must include the ability to blink, as it has been inherited however with the way it is set up, it allows for the specific action to be defined within the Happy class itself. 
> This means that each subclass can in fact blink in its own way (for example with varying delay times) but with the method name remaining consistent.
>
1. **Implement Blink in Sad Class:**

   - Create a new method called `blink` within the Sad class. Ensure you use the same method signature as in the Happy class:

   ```python
    def blink(self, delay = 0.50):
        self.draw_eyes(wide_open=False)
        self.show()
        time.sleep(delay)
        self.draw_eyes(wide_open=True)
        self.show()
   ```

2. **Code Implementation:** Implement the code that allows the Sad smiley to blink. Use the implementation from the Happy Smiley as a reference. Ensure your new method functions similarly by controlling the blink duration through the `delay` argument.

3. **Testing the Implementation:**

- Test the new blink functionality on your Raspberry Pi or within the Python classes provided. You might need to adjust the `main.py` script to incorporate Sad Smiley's new blinking capability.

Include a screenshot of the sad smiley or the modified `main.py`:

![Sad Smiley Blinking](screenshots/main.py_update_sad.png)

- Observe and document the Sad smiley as it blinks its eyes. Describe any adjustments or issues encountered during implementation.

  > A couple of adjustments were required to successfully implement a blinking sad smiley, these were that the Sad class had to be imported into the main.py file and the defined smiley variable within the main() function needed to be updated to reference Sad() rather than Happy().

  ### 2.8. If It Walks Like a Duck…

  Previously, you implemented the blink functionality for the Sad smiley without utilizing the class `Blinkable`. Assuming you did not use `Blinkable` (even if you actually did), consider how the Sad smiley could blink similarly to the Happy smiley without this specific class.

  1. **Class Type Analysis:** What kind of class is `Blinkable`? Inspect its superclass for clues about its classification.

     > The Blinkable class is an abstract base class.

  2. **Class Implementation:** `Blinkable` is a class intended to be implemented by other classes. What generic term describes this kind of class, which is designed for implementation by others? **Clue**: Notice the lack of any concrete implementation and the naming convention.

  > Abstract base class

  3. **OO Principle Identification:** Regarding your answer to question (2), which Object-Oriented (OO) principle does this represent? Choose from the following and justify your answer in 1-2 sentences: Abstraction, Polymorphism, Inheritance, Encapsulation.

  > It represents the Abstraction principle. The class does not contain detail or implementation of how the blink function operates, only that it is present and that it will be inherited by child classes.

  4. **Implementation Flexibility:** Explain why you could grant the Sad Smiley a blinking feature similar to the Happy Smiley's implementation, even without directly using `Blinkable`.

  > By defining a blink function directly into the Sad class, it enabled the sad smiley to perform a blink despite the fact that it did not inherit the attributes of the Blinkable class.

  5. **Concept and Language Specificity:** In relation to your response to question (4), what is this capability known as, and why is it feasible in Python and many other dynamically typed languages but not in most statically typed programming languages like C#? **Clue** This concept is hinted at in the title of this section.

  > This capabilty is known as Duck typing. The reason that it can work in python, and other dynamically typed languages is that the object is defined at the time they run, and based on their attributes rather than being explicitly defined. 
  > Conversely, in a statically typed languages this doesn't work as the object needs to be declared to a specific class for compiling and the attributes of an object cannot overwrite this.

  ***

  ## 3. Refactoring

  ### 3.1. Does a Smiley Have to Be Yellow?

  While our current implementation predominantly features yellow smileys, emotional expressions like sickness or anger typically utilize colors like green, red, or orange. We'll explore the feasibility of integrating these colors into our smileys.

  1. **Defined Colors and Their Location:**

     1. Which colors are defined and in which class(s)?
        > The colours of WHITE, GREEN, RED, YELLOW and BLACK are defined within the Smiley class.
     2. What type of variables hold these colors? Are the values expected to change during the program's execution? Explain your answer.
        > There variables for each colour are contained within a tuple, these are not expected to change at all during execution of the program as tuples are immutable and so the values cannot be changed once they have been created.
     3. Add the color blue to the appropriate class using the appropriate format and values.
        > BLUE = (0, 0, 255)

  2. **Usage of Color Variables:**

     1. In which classes are the color variables used?
        > The colour variables are used in each of the Smiley, Happy and Sad classes.

  3. **Simple Method to Change Colors:**
  4. What is the easiest way you can think to change the smileys to green? Easiest, not necessarily the best!
     > The easiest way to change the colour of the smiley to green is to update the YELLOW variable defined in the Smiley class to a value of (0, 255, 0) as this will result in the colour appearing as green wherever the YELLOW variable is used. 
     > As a result, this only requires one change to the entire code to make the effect.

  Here's a revised version of the "Flexible Colors – Step 1" section for the smiley project, incorporating your specifications for formatting and content updates:

  ### 3.2. Flexible Colors – Step 1

  Changing the color of the smileys once is straightforward, but it isn't very flexible. To facilitate various colors for smileys, it is advisable not to hardcode values in any class. This approach was identified earlier as a necessary change. Let's start by removing the built-in assumptions about color in our classes.

  1. **Add a method called `complexion` to the `Smiley` class:** Implement this instance method to return `self.YELLOW`. Using the term "complexion" instead of "color" provides a more abstract terminology that focuses on the meaning rather than implementation.
     > complexion(self) method was added to the Smiley class within code, changes were commited to git.

  2. **Refactor subclasses to use the `complexion` method:** Modify any subclass that directly accesses the color variable to instead utilize the new `complexion` method. This ensures that color handling is centralized and can be easily modified in the future.
    > Changes were made to both the Happy and Sad classes to utilise the complexion method, changes to code were commited to git.

  3. **Determine the applicable Object-Oriented principle:** Consider whether Abstraction, Polymorphism, Inheritance, or Encapsulation best applies to the modifications made in this step.
     > Encapsulation best fits the use of the new complexion method, as the method is called and the details of the specific code for setting the colour itself is displayed within this.

  4. **Verify the implementation:** Ensure that the modifications function as expected. The smileys should still display in yellow, confirming that the new method correctly replaces the direct color references.
     > Implementation was tested and running correctly, smiley displayed yellow while utilising the complexion method.

  This step is crucial for setting up a more flexible system for color management in the smiley display logic, allowing for easy adjustments and extensions in the future.

  ### 3.3. Flexible Colors – Step 2

  Having removed the hardcoded color values, we now enhance the base class to support dynamic color assignments more effectively.

  1. **Modify the `__init__()` method in the `Smiley` class:** Introduce a default argument named `complexion` and assign `YELLOW` as its default value. This allows the instantiation of smileys with customizable colors.
     > Smiley '__init__()' method updated to include complexion argument with default value of YELLOW, changes commited to git.

  2. **Introduce a new instance variable:** Create a variable called `my_complexion` and assign the `complexion` parameter to it. This step ensures that each smiley instance can maintain its own color state.
     > Instance variable created and complexion method updated to access the my_complexion variable, changes commited to git.

  3. **Rationale for `my_complexion`:** Using a distinct instance variable like `my_complexion` avoids potential conflicts with the method parameter names and clarifies that it is an attribute specific to the object.

  4. **Bulk rename:** We want to update our grid to use the value of complexion, but we have so many `Y`'s in the grid. Use your IDE's refactoring tool to rename all instances of the **symbol** `Y` to `X`. Where `X` is the value of the `complexion` variable. Include a screenshot evidencing you have found the correct refactor tool and the changes made.

  ![Bulk Rename](screenshots/3.3_screenshot_bulk_rename.png)
-  ![Bulk Rename](screenshots/3.3_screenshot_bulk_rename2.png)

  5. **Update the `complexion` method:** Adjust this method to return `self.my_complexion`, ensuring that whatever color is assigned during instantiation is what the smiley displays.
     > complexion method has been updated to reference the my_complexion method.

  6. **Verification:** Run the updated code to confirm that Smileys still defaults to yellow unless specified otherwise.
     > code was run for test and confirmed working as expected.

  ### 3.4. Flexible Colors – Step 3

  With the foundational changes in place, it's now possible to implement varied smiley colors for different emotional expressions.

  1. **Adjust the `Sad` class initialization:** In the `Sad` class's initializer method, change the superclass call to include the `complexion` argument with the value `self.BLUE`, as shown:

     ```python
     super().__init__(complexion=self.BLUE)
     ```

  2. **Test color functionality for the Sad smiley:** Execute the program to verify that the Sad smiley now appears blue.
     > Program was run successfully with the sad smiley appearing blue.

  3. **Ensure the Happy smiley remains yellow:** Confirm that changes to the Sad smiley do not affect the default color of the Happy smiley, which should still display in yellow.
     > Additional test with main.py calling Happy smiley was run and confirmed appeared yellow.

  4. **Design and Implement An Angry Smiley:** Create an Angry smiley class that inherits from the `Smiley` class. Set the color of the Angry smiley to red by passing `self.RED` as the `complexion` argument in the superclass call.
     > Angry class has been implemented and tested successfully.

  ***
