# lesson-12

## FUNCTIONS
#### FUNCTIONS EXAMPLE
```python
def printStuff():
    print("HELLO! I'm a function")

def pow(x, y):
    result = 1;
    for i in range(y):
        result *= x
    return result

printStuff()
print(pow(2,3))
```

## CLASSES
#### CLASSES EXAMPLE

<img src="classes.png " alt="drawing" style="width:500px;"/>

Image: https://brilliant.org/wiki/classes-oop/

```py
# https://brilliant.org/wiki/classes-oop/
class Car(object):
    def __init__(self, model, passengers, color, speed):
        self.model = model
        self.passengers = passengers
        self.color = color
        self.speed = speed

    def accelerate(self):
        self.speed = self.speed + 2
        print (self.model, "accelerate!", self.speed)

bmw = Car("BMW", 4, "red", 5)
ferrari = Car("Ferrari", 2, "black", 10)
ford = Car("Ford", 6, "blue", 6)

bmw.accelerate()
print ("BMW color", bmw.color)

ferrari.accelerate()
print ("Ferrari color",  ferrari.color)
ferrari.accelerate() #note that the speed has been updated from the previous accelerate call

print ("Ford Passengers", ford.passengers)
ford.accelerate()
```




## THE CRITTER CARETAKER PROGRAM
#### FULL PROGRAM
```python
# Critter Caretaker
# A virtual pet to care for

class Critter(object):
    """A virtual pet"""
    def __init__(self, name, hunger = 0, boredom = 0):
        self.name = name
        self.hunger = hunger
        self.boredom = boredom

    def __pass_time(self):
        self.hunger += 1
        self.boredom += 1

    @property
    def mood(self):
        unhappiness = self.hunger + self.boredom
        if unhappiness < 5:
            m = "happy"
        elif 5 <= unhappiness <= 10:
            m = "okay"
        elif 11 <= unhappiness <= 15:
            m = "frustrated"
        else:
            m = "mad"
        return m

    def talk(self):
        print("I'm", self.name, "and I feel", self.mood, "now.\n")
        self.__pass_time()

    def eat(self, food = 4):
        print("Brruppp.  Thank you.")
        self.hunger -= food
        if self.hunger < 0:
            self.hunger = 0
        self.__pass_time()

    def play(self, fun = 4):
        print("Wheee!")
        self.boredom -= fun
        if self.boredom < 0:
            self.boredom = 0
        self.__pass_time()


def main():
    crit_name = input("What do you want to name your critter?: ")
    crit = Critter(crit_name)

    choice = None  
    while choice != "0":
        print \
        ("""
        Critter Caretaker

        0 - Quit
        1 - Listen to your critter
        2 - Feed your critter
        3 - Play with your critter
        """)

        choice = input("Choice: ")
        print()

        # exit
        if choice == "0":
            print("Good-bye.")

        # listen to your critter
        elif choice == "1":
            crit.talk()

        # feed your critter
        elif choice == "2":
            crit.eat()

        # play with your critter
        elif choice == "3":
            crit.play()

        # some unknown choice
        else:
            print("\nSorry, but", choice, "isn't a valid choice.")

main()
("\n\nPress the enter key to exit.")
```

Helpful Resources:
- **__init__** is the constructor. Constructors are used to initializing the object’s state. The task of constructors is to initialize(assign values) to the data members of the class when an object of the class is created. https://www.geeksforgeeks.org/__init__-in-python/
- **__pass_time()** - The double underscore __ prefixed to a variable makes it private. It gives a strong suggestion not to touch it from outside the class. Any attempt to do so will result in an AttributeError. https://www.tutorialsteacher.com/python/public-private-protected-modifiers
- **@property** https://www.programiz.com/python-programming/property, https://programiz.com/python-programming/decorator


## MAKE OUR OWN PYTHON CLASS!

## HOMEWORK
- hw link (you can work in teams): https://classroom.github.com/a/-yTUqSSn
- highly reccomend having at least one test case passing before the end of class
