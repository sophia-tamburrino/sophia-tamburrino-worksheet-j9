## #1 - What is the difference between a design pattern and a java library?
A design pattern contains techniques and templates on how to program something. A Java library you can import and use the methods to assist in making a program, but a design pattern is a concept.
## #2 - Using the Singleton pattern, write code/pseudocode that ensures that only one database connection object is ever instantiated.
```Java
public class Singleton {
    private static Singleton databaseInstance;

    private Singleton() {
        //in here, set up the database object.
        //connect to the database in here
    }

    // Method to get an instance of this class.
    public static Singleton getInstance() {
        if (databaseInstance == null) {
            databaseInstance = new Singleton();
        }

        return databaseInstance;
    }
}
```
## #3 - Using the Factory pattern, write code/pseudocode that sets up a factory for two child classes of Animal: Bird and Mammal. Each of these has a constructor with the same arguments as those of the parent class.
```Java
public class ItemFactory {

  public static Item getItem(String itemType, ...list of inputs that could be sent to parent class constuctor...){
      switch(itemType){
          case "Bird":
              return new Bird("Bluejay", 1);
          case "Mammal":
              return new Mammal("Turtle", 20);   
      }
    return null;
  }
}
```

## #4 - Use the Adapter pattern to allow us to use the Mammal class with the Aquarium class above. Each animal is housed alone in its cage during its visit. All mammals are given the same medication, namely, "antibiotics".
```Java
public class Adapter extends Aquarium {
    private Mammal mam;
    public Adapter(Mammal in){
        mam = in;
    }
    public void feedAll(ArrayList<Fish> tanks, int numFishInTank) {}
	public void cleanAll(ArrayList<Fish> tanks) {}
}
```
## #5 - What is the benefit of the Bridge design pattern? Why use one?
Bridge design patters utelize aggregation through a single class that only takes a type of configuration and a type of logging. Using some classes and interfaces instead of many child classes is more efficient.

