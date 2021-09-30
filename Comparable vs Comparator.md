# Comparable Interface
The Comparable interface defines the `compareTo` method used to compare objects. If a class implements the Comparable interface, objects created from that class can be sorted using Java's sorting algorithms.

The `compareTo` method required by the Comparable interface receives as its parameter the object to which the `this` object is compared. If the `this` object comes before the object received as a parameter in terms of sorting order, the method should return a negative number. If, on the other hand, the "this" object comes after the object received as a parameter, the method should return a positive number. Otherwise, 0 is returned. The sorting resulting from the compareTo method is called natural ordering.
