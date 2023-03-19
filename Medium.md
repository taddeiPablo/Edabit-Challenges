# Medium


## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>
### Array of Multiples
Create a function that takes two numbers as arguments (num, length) and returns an array of multiples of num until the array length reaches length. https://edabit.com/challenge/2QvnWexKoLfcJkSsc

### Instrucciones
Create a function that takes two numbers as arguments (num, length) and returns an array of multiples of num until the array length reaches length.

### Ejemplos
+ ArrayOfMultiples(7, 5) ➞ [7, 14, 21, 28, 35]
+ ArrayOfMultiples(12, 10) ➞ [12, 24, 36, 48, 60, 72, 84, 96, 108, 120]
+ ArrayOfMultiples(17, 6) ➞ [17, 34, 51, 68, 85, 102]

### Notas
+ Notice that num is also included in the returned array.

## Codigo Realizado :
```cs
using System;

public class Program {
	public static int[] ArrayOfMultiples(int num, int length) {
		int[] result = new int[length];
		for(int index=0;index<length;index++)
		{
			result[index] =  num * (index+1);
		}
		return result;
	}
}
```

## Codigo de Prueba :
```cs
	[Test]
	[TestCase(7, 5, Result = new int[] { 7, 14, 21, 28, 35 })]
	[TestCase(12, 10, Result = new int[] { 12, 24, 36, 48, 60, 72, 84, 96, 108, 120 })]
	[TestCase(17, 7, Result = new int[] { 17, 34, 51, 68, 85, 102, 119 })]
	[TestCase(630, 14, Result = new int[] { 630, 1260, 1890, 2520, 3150, 3780, 4410, 5040, 5670, 6300, 6930, 7560, 8190, 8820 })]
	[TestCase(140, 3, Result = new int[] { 140, 280, 420 })]
	[TestCase(7, 8, Result = new int[] { 7, 14, 21, 28, 35, 42, 49, 56 })]
	[TestCase(11, 21, Result = new int[] { 11, 22, 33, 44, 55, 66, 77, 88, 99, 110, 121, 132, 143, 154, 165, 176, 187, 198, 209, 220, 231 })]
	public static int[] FixedTest(int num, int len) => Program.ArrayOfMultiples(num, len);
```
## Estimacion :
5 minutos

## Actual Duracion :
3 minuto

<hr>

## <u>2. Segundo Ejercicio </u>
### Return the Middle Character(s) of a String
Create a function that takes a string and returns the middle character(s). If the word's length is odd, return the middle character. If the word's length is even, return the middle two characters. https://edabit.com/challenge/JF25KTZEcPzXhBvpM

### Instrucciones
Create a function that takes a string and returns the middle character(s). If the word's length is odd, return the middle character. If the word's length is even, return the middle two characters.

### Ejemplos
+ GetMiddle("test") ➞ "es"
+ GetMiddle("testing") ➞ "t"
+ GetMiddle("middle") ➞ "dd"
+ GetMiddle("A") ➞ "A"

### Notas
+ All test cases contain a single word (as a string).

## Codigo Realizado :
```cs
public class Program 
{
	public static string GetMiddle(string str) 
	{
		int num = str.Length /2;
		string result = "";
		if(str.Length % 2 == 0){
			string str1 = str[num -1].ToString();
			string str2 = str[num].ToString();
			result = str1 + str2;
		}else{
			result = str[num].ToString(); 
		}
		return result;
	}
}
```

## Codigo de Prueba :
```cs
[Test]
  [TestCase("test", Result="es")]
  [TestCase("testing", Result="t")]
  [TestCase("middle", Result="dd")]
  [TestCase("A", Result="A")]
  [TestCase("inhabitant", Result="bi")]
  [TestCase("brown", Result="o")]
  [TestCase("pawn", Result="aw")]
  [TestCase("cabinet", Result="i")]
  [TestCase("fresh", Result="e")]
  [TestCase("shorts", Result="or")]
    public static string FixedTest(string str)
    {
        return Program.GetMiddle(str);
    }
```
## Estimacion :
6 minutos

## Actual Duracion :
4 minuto

<hr>

## <u>3. Tercer Ejercicio </u>
### Fraction Greater Than One
Given a fraction as a string, return whether or not it is greater than 1 when evaluated. https://edabit.com/challenge/7KX5NogxnTzrKEd5P

### Instrucciones
Given a fraction as a string, return whether or not it is greater than 1 when evaluated.

### Ejemplos
+ GreaterThanOne("1/2") ➞ false
+ GreaterThanOne("7/4") ➞ true
+ GreaterThanOne("10/10") ➞ false

### Notas
+ Fractions must be strictly greater than 1 (see example #3).

## Codigo Realizado :
```cs
public class Program
{
	public static bool GreaterThanOne(string str)
	{
		double num1;
		double num2;
		string[] arr = str.Split('/');
		num1 = double.Parse(arr[0]);
		num2 = double.Parse(arr[1]);
		if(num1/num2 > 1){
			return true;
		}else{
			return false;
		}
	}
}
```

## Codigo de Prueba :
```cs
[Test]
[TestCase("1/2", Result =  false)]
[TestCase("7/4", Result =  true)]
[TestCase("10/10", Result =  false)]
[TestCase("12/30", Result =  false)]
[TestCase("28/3", Result =  true)]
[TestCase("35/31", Result =  true)]
[TestCase("11/27", Result =  false)]
[TestCase("42/32", Result =  true)]
[TestCase("34/15", Result =  true)]
[TestCase("16/16", Result =  false)]
[TestCase("38/41", Result =  false)]
[TestCase("45/43", Result =  true)]
[TestCase("13/38", Result =  false)]
[TestCase("43/2", Result =  true)]
[TestCase("16/31", Result =  false)]
[TestCase("41/15", Result =  true)]
[TestCase("2/38", Result =  false)]
[TestCase("37/21", Result =  true)]
    public static bool FixedTest(string a)
    {
        return Program.GreaterThanOne(a);
    }
```
## Estimacion :
5 minutos

## Actual Duracion :
3 minuto

