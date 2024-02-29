# LINQ and Lambda expressions in C#
LINQ (Language-Integrated Query) and Lambda expressions are powerful features in C# that allow developers to query and manipulate data concisely and expressively. While both are used for similar purposes, they have distinct syntaxes and use cases. Let's explain with examples and provide multiple scenarios to illustrate the usage of LINQ and Lambda expressions in C#.

You can visit my blog post- [Understanding LINQ and Lambda Expressions in C#](https://binarybytez.com/understanding-linq-and-lambda-expressions/)

## 1. LINQ (Language-Integrated Query):
**LINQ** is a set of features in C# that enables developers to query data from different data sources using a SQL-like syntax directly within the C# language.

**Syntax:** LINQ syntax consists of keywords such as from, where, select, group by, order by, etc., which resemble SQL syntax.
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
var evenNumbers = from num in numbers
                  where num % 2 == 0
                  select num;
```

## 2. Lambda Expressions:
**Lambda expressions** are anonymous functions that allow developers to write inline delegate functions without explicitly defining a method.

**Syntax:** Lambda expressions consist of the => (arrow) operator, parameters, and an expression or statement block.
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
var evenNumbers = numbers.Where(num => num % 2 == 0);
```

## Examples with multiple scenarios

**1. Filtering a List of Objects:**

**Using LINQ:**
```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
var evenNumbers = from num in numbers
                  where num % 2 == 0
                  select num;
```

**Using Lambda Expression:**
```csharp
var evenNumbers = numbers.Where(num => num % 2 == 0);
```

**2. Sorting a List of Objects:**

**Using LINQ:**
```csharp
List<string> fruits = new List<string> { "Apple", "Banana", "Orange", "Grape" };
var sortedFruits = from fruit in fruits
                   orderby fruit descending
                   select fruit;
```

**Using Lambda Expression:**
```csharp
var sortedFruits = fruits.OrderByDescending(fruit => fruit);
```

**3. Selecting Specific Properties from a List of Objects:**

**Using LINQ:**
```csharp
List<Person> people = new List<Person>
{
    new Person { Name = "Alice", Age = 25 },
    new Person { Name = "Bob", Age = 30 },
    new Person { Name = "Charlie", Age = 28 }
};
var names = from person in people
            select person.Name;
```

**Using Lambda Expression:**
```csharp
var names = people.Select(person => person.Name);
```

**4. Filtering and Projecting Data from a List of Objects:**

**Using LINQ:**
```csharp
List<Person> people = new List<Person>
{
    new Person { Name = "Alice", Age = 25 },
    new Person { Name = "Bob", Age = 30 },
    new Person { Name = "Charlie", Age = 28 }
};
var adults = from person in people
             where person.Age >= 18
             select new { person.Name, person.Age };
```

**Using Lambda Expression:**
```csharp
var adults = people.Where(person => person.Age >= 18)
                  .Select(person => new { person.Name, person.Age });
```

**5. Grouping Data from a List of Objects:**

**Using LINQ:**
```csharp
List<Person> people = new List<Person>
{
    new Person { Name = "Alice", Age = 25 },
    new Person { Name = "Bob", Age = 30 },
    new Person { Name = "Charlie", Age = 28 }
};
var ageGroups = from person in people
               group person by person.Age < 30 into youngGroup
               select new
               {
                   IsYoung = youngGroup.Key,
                   People = youngGroup.ToList()
               };
```

**Using Lambda Expression:**
```csharp
var ageGroups = people.GroupBy(person => person.Age < 30)
                     .Select(youngGroup => new
                     {
                         IsYoung = youngGroup.Key,
                         People = youngGroup.ToList()
                     });
```

These examples demonstrate various scenarios where LINQ and Lambda expressions are used to query, filter, project, sort, and group data in C#. By understanding and mastering these features, developers can write concise and expressive code for data manipulation tasks.

**Note:** The `Person` class used in these examples is assumed to have properties `Name` and `Age`.

Feel free to ask if you have any questions or need further clarification! [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kawser2133)
