# Comparable Interface
> The Comparable interface defines the `compareTo` method used to compare objects. If a class implements the Comparable interface, objects created from that class can be sorted using Java's **sorting algorithms**.



The `compareTo` method compares the current object with the object sent as a parameter.

When implementing it, we need to make sure that the method returns:
* A positive integer, if the current object is greater than the parameter object
* A negative integer, if the current object is less than the parameter object
* Zero, if the current object is equal to the parameter object

In mathematics, we call this a sign or a signum function:
   
   ![aaa](https://www.baeldung.com/wp-content/uploads/2021/02/2021-01-24-10_27_03-notation-What-does-sgn-mean_-Mathematics-Stack-Exchange.png)

#### Example :

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
	@Override
	public int compareTo(Movie m)
	{
		return this.year.compareTo(m.year);
	}
  
}

public class ComparableDemo {
	public static void main(String[] args) {
		List<Movie> list = Arrays.asList(
			new Movie("Force Awakens", 8.3, 2015),
			new Movie("Star Wars", 8.7, 1977),
			new Movie("Empire Strikes Back", 8.8, 1980),
			new Movie("Return of the Jedi", 8.4, 1983)
		);
		
		Collections.sort(list);
	}
}
```
__Result:__
```java
Movies after sorting : 
- 1977 Star Wars 8.7 
- 1980 Empire Strikes Back 8.8 
- 1983 Return of the Jedi 8.4 
- 2015 Force Awakens 8.3 
```
#### Subtraction Pattern of `compareTO`
``` java
@Override
public int compareTo(Movie m)
{
	return this.year - m.year;
}
```
### Sort Order
>This interface imposes a `total ordering` on the objects of each class that implements it. This ordering is referred to as the class's `natural ordering`, and the class's compareTo method is referred to as its natural comparison method.

In a word, natural ordering is a default total ordering for Comparable Interface, if you don't change override the `compareTo()` function.

#### Natural ordering:
  * For String(or Charater object), `Natural ordering` is `unicode values`.
  * For Integer, it is `ascending order`, like 1,2,3,4,...
