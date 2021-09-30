# Comparable Interface
> The Comparable interface defines the `compareTo` method used to compare objects. If a class implements the Comparable interface, objects created from that class can be sorted using Java's **sorting algorithms**.



The `compareTo` method compares the current object with the object sent as a parameter.

When implementing it, we need to make sure that the method returns:
* A positive integer, if the current object is greater than the parameter object
* A negative integer, if the current object is less than the parameter object
* Zero, if the current object is equal to the parameter object

In mathematics, we call this a sign or a signum function:
   
   ![aaa](https://www.baeldung.com/wp-content/uploads/2021/02/2021-01-24-10_27_03-notation-What-does-sgn-mean_-Mathematics-Stack-Exchange.png)

Example :

``` java
class Movie implements Comparable<Movie>
{
    private double rating;
    private String name;
    private int year;
	
 	// Constructor
    public Movie(String nm, double rt, int yr)
    {
        this.name = nm;
        this.rating = rt;
        this.year = yr;
    }
    
    // Getter methods for accessing private data
    public double getRating() { return rating; }
    public String getName()   {  return name; }
    public int getYear()      {  return year;  }
    
    // Used to sort movies by year
    public int compareTo(Movie m)
    {
        return this.year.compareTo(m.year);
    }
  
}
```
**Subtraction Pattern of ** `compareTO`
``` java
	public int compareTo(Movie m)
    {
        return this.year - m.year;
    }
```
