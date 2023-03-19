# Easy


## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>
### Absolute Sum
Take an array of integers (positive or negative or both) and return the sum of the absolute value of each element https://edabit.com/challenge/J3WGSreYhc65cWyrc

### Instrucciones
Take an array of integers (positive or negative or both) and return the sum of the absolute value of each element.

### Ejemplos
+ getAbsSum([2, -1, 4, 8, 10]) ➞ 25
+ getAbsSum([-3, -4, -10, -2, -3]) ➞ 22
+ getAbsSum([2, 4, 6, 8, 10]) ➞ 30
+ getAbsSum([-1]) ➞ 1

### Notas
+ The term "absolute value" means to remove any negative sign in front of a number, and to think of all numbers as positive (or zero).
+ All the elements in the given array are integers.

## Codigo Realizado :
```cs
public class Program 
{
    public static int GetAbsSum(int[] arr) 
    {
			int[] results = new int[arr.Length];
			for(int index=0; index<arr.Length; index++)
			{
				results[index] = Math.Abs(arr[index]);
			}
			int sumaItems =0;
			for(int index=0; index<results.Length; index++)
			{
				sumaItems += results[index];
			}
			return sumaItems;
    }
}
```

## Codigo de Prueba :
```cs
[Test]
  [TestCase(new int[] { 2, -1, -3, 4, 8 }, Result=18)]
  [TestCase(new int[] { -1 }, Result=1)]
  [TestCase(new int[] { -1, -3, -5, -4, -10, 0 }, Result=23)]
  [TestCase(new int[] { 8, 9, 10, 32, 101, -10 }, Result=170)]
  [TestCase(new int[] { 500 }, Result=500)]
    public static int FixedTest(int[] arr)
    {
        return Program.GetAbsSum(arr);
    }
```
## Estimacion :
4 minutos

## Actual Duracion :
2 minuto

<hr>

## <u>2. Segundo Ejercicio </u>
### To the Power of _____
Create a function that takes a base number and an exponent number and returns the calculation. https://edabit.com/challenge/esARjHfWfdRP6ePEC

### Instrucciones
Create a function that takes a base number and an exponent number and returns the calculation.

### Ejemplos
+ СalculateExponent(5, 5) ➞ 3125
+ СalculateExponent(10, 10) ➞ 10000000000
+ СalculateExponent(3, 3) ➞ 27

### Notas
+ All test inputs will be positive integers.
+ Don't forget to return the result.
+ If you get stuck on a challenge, find help in the Resources tab.
+ If you're really stuck, unlock solutions in the Solutions tab.

## Codigo Realizado :
```cs
using System;
public class Program 
{
    public static long CalculateExponent(long number, long exponent) 
    {
			long result = number;
			for(int index=1;index<exponent;index++)
			{
				result *= number;
			}
			return result;
    }
}
```

## Codigo de Prueba :
```cs
[Test]
		[TestCase(5,5, Result=3125)]
		[TestCase(3,3, Result=27)]
		[TestCase(10,10, Result=10000000000)]
    public static long CalculateExponent(long number, long exponent) 
    {
				Console.WriteLine($"Input: {number}, {exponent}");
        return Program.CalculateExponent(number, exponent);
    }
```
## Estimacion :
3 minutos

## Actual Duracion :
2 minuto

<hr>

## <u>3. Tercer Ejercicio </u>
### Multiply by Length
Create a function to multiply all of the values in an array by the amount of values in the given array https://edabit.com/challenge/7KX5NogxnTzrKEd5P

### Instrucciones
Create a function to multiply all of the values in an array by the amount of values in the given array.

### Ejemplos
+ MultiplyByLength([2, 3, 1, 0]) ➞ [8, 12, 4, 0]
+ MultiplyByLength([4, 1, 1]) ➞ ([12, 3, 3])
+ MultiplyByLength([1, 0, 3, 3, 7, 2, 1]) ➞  [7, 0, 21, 21, 49, 14, 7]
+ MultiplyByLength([0]) ➞ ([0])

### Notas
+ All of the values given are numbers.
+ All arrays will have at least one element.
+ Don't forget to return the result.

## Codigo Realizado :
```cs
public class Program
{
	public static int[] MultiplyByLength(int[] arr)
	{
	  int[] result = new int[arr.Length];
		for(int index=0; index<arr.Length; index++)
		{
			result[index] = arr[index] * arr.Length;
		}
		return result;
	}
}
```

## Codigo de Prueba :
```cs
[Test]
		public void BasicTests()
		{
			int[] i1 = {2, 6, 4, 9}; 
			int[] i2 = {4, 1, 1};
			int[] i3 = {1, 0, 3, 3, 7, 2, 1}; 
			int[] i4 = {0}; 
			
			int[] o1 = {8, 24, 16, 36}; 
			int[] o2 = {12, 3, 3};
			int[] o3 = {7, 0, 21, 21, 49, 14, 7}; 
			int[] o4 = {0}; 
			
			Assert.AreEqual(o1, Program.MultiplyByLength(i1));
			Assert.AreEqual(o2, Program.MultiplyByLength(i2));
			Assert.AreEqual(o3, Program.MultiplyByLength(i3));
			Assert.AreEqual(o4, Program.MultiplyByLength(i4));
		}
```
## Estimacion :
4 minutos

## Actual Duracion :
2 minuto
