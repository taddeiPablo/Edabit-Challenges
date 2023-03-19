
# Very Easy


## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>
### Convert Age to Days
Create a function that takes the age in years and returns the age in days https://edabit.com/challenge/nkkKguC5TgWnBiMLA

### Instrucciones
Create a function that takes the age in years and returns the age in days.

### Ejemplos
+ CalcAge(65) ➞ 23725
+ CalcAge(0) ➞ 0
+ CalcAge(20) ➞ 7300

### Notas
+ Use 365 days as the length of a year for this challenge.
+ Ignore leap years and days between last birthday and now.
+ Expect only positive integer inputs.

## Codigo Realizado :
```cs
public class Program 
{
    public static int CalcAge(int age) 
    {
	return age * 365;
    }
}
```

## Codigo de Prueba :
```cs
[TestFixture]
public class Tests {
	[Test]
	[TestCase(10, Result=3650)]
	[TestCase(0, Result=0)]
	[TestCase(73, Result=26645)]
	public static int CalcAge(int age)
	{
		return Program.CalcAge(age);
	}
}
```
## Estimacion :
2 minutos

## Actual Duracion :
1 minuto

<hr>

## <u>2. Segundo Ejercicio </u>
### Are the Numbers Equal?
Create a function that takes two integers and checks if they are equal https://edabit.com/challenge/oDnoAHEnAsL78sQh9

### Instrucciones
Create a function that takes two integers and checks if they are equal.

### Ejemplos
+ IsEqual(5, 6) ➞ false
+ IsEqual(1, 1) ➞ true
+ IsEqual(36, 35) ➞ false

### Notas
+ N/A

## Codigo Realizado :
```cs
public class Program 
{
   public static bool IsEqual(int num1, int num2)
   {
     return num1 == num2;
   }
}
```

## Codigo de Prueba :
```cs
[TestFixture]
public class Tests
{
	[Test]
	[TestCase(2, 2, Result=true)]
	[TestCase(88, 88, Result=true)]
	[TestCase(36, 35, Result=false)]
	[TestCase(1, 1, Result=true)]
	[TestCase(5, 6, Result=false)]
	public static bool FixedTest(int num1, int num2) =>
		Program.IsEqual(num1, num2);
}
```
## Estimacion :
2 minutos

## Actual Duracion :
1 minuto

<hr>

## <u>3. Tercer Ejercicio </u>
### Is the Number Less than or Equal to Zero?
Create a function that takes a number as its only argument and returns true if it's less than or equal to zero, otherwise return https://edabit.com/challenge/7KX5NogxnTzrKEd5P

### Instrucciones
Create a function that takes a number as its only argument and returns true if it's less than or equal to zero, otherwise return false.

### Ejemplos
+ lessThanOrEqualToZero(5) ➞ false
+ lessThanOrEqualToZero(0) ➞ true
+ lessThanOrEqualToZero(-2) ➞ true

### Notas
+ Don't forget to return the result.
+ If you get stuck on a challenge, find help in the Resources tab.
+ If you're really stuck, unlock solutions in the Solutions tab.

## Codigo Realizado :
```cs
public class Program 
{
    public static bool LessThanOrEqualToZero(double a) 
    {
    	return a <= 0 ? true : false;
    }
}
```

## Codigo de Prueba :
```cs
[Test]
  [TestCase(5, Result=false)]
  [TestCase(0, Result=true)]
  [TestCase(-5, Result=true)]
  [TestCase(1, Result=false)]
  [TestCase(2, Result=false)]
  [TestCase(1000, Result=false)]
  [TestCase(0.5, Result=false)]
    public static bool FixedTest(double a)
    {
        return Program.LessThanOrEqualToZero(a);
    }
```
## Estimacion :
2 minutos

## Actual Duracion :
1 minuto

