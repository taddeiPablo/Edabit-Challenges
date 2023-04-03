# Very Hard

## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>

### Instrucciones
A Fibonacci Word is a specific sequence of binary digits (or symbols from any two-letter alphabet). The Fibonacci Word is formed by repeated concatenation in the same way that the Fibonacci numbers are formed by repeated addition.
Create a function that takes a number n as an argument and returns the first n elements of the Fibonacci Word sequence.
If n < 2, the function must return "invalid".

## Codigo Realizado :
```cs
using System;
using System.Collections.Generic;

public class Program
{
    public static string FiboWord(int n) {
		        if (n < 2){
					return "invalid";
				}

            string prev = "b";
            string next = "a";

            List<string> words = new List<string>()
						{
							"b",
							"a"
						};

            for (int i=0; i<n-2; i++)
            {
                string temp = next;
                next += prev;
                prev = temp;

                words.Add(next);
            }

            return string.Join(", ", words);
	}
}
```

## Codigo de Prueba :
```cs
using NUnit.Framework;
using System;

[TestFixture]
public class Tests
{
	[TestCase(1, Result="invalid")]
	[TestCase(3, Result="b, a, ab")]
	[TestCase(7, Result="b, a, ab, aba, abaab, abaababa, abaababaabaab")]
	[TestCase(10, Result="b, a, ab, aba, abaab, abaababa, abaababaabaab, abaababaabaababaababa, abaababaabaababaababaabaababaabaab, abaababaabaababaababaabaababaabaababaababaabaababaababa")]
	[TestCase(15, Result="b, a, ab, aba, abaab, abaababa, abaababaabaab, abaababaabaababaababa, abaababaabaababaababaabaababaabaab, abaababaabaababaababaabaababaabaababaababaabaababaababa, abaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaab, abaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababa, abaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaab, abaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababa, abaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaababaababaabaababaababaabaababaabaababaababaabaababaabaab")]
  	public static string TestSolution(int n)
    {
        return Program.FiboWord(n);
    }
}
```
## Estimacion :
40 minutos

## Actual Duracion :
40 minuto

<hr>

## <u>2. Segundo Ejercicio </u>

### Instrucciones
Write a function that calculates overtime and pay associated with overtime.
Working 9 to 5: regular hours
After 5pm is overtime
Your function gets an array with 4 values:

Start of working day, in decimal format, (24-hour day notation)
End of working day. (Same format)
Hourly rate
Overtime multiplier
Your function should spit out:

$ + earned that day (rounded to the nearest hundreth)

## Codigo Realizado :
```cs
public class Challenge 
{
	public static string OverTime(double[] arr) {
        double start = arr[0];
				double end = arr[1];
				double rate = arr[2]; 
		    double mult = arr[3];
		
        double regular;
				double overtime;
		
        if (start <= 17d) {
					
            if (end > 17d) {
                regular = (17d - start) * rate;
                overtime = (end - 17d) * rate * mult;
            }
            else {
                regular = (end - start) * rate;
                overtime = 0d;
            }
        }
        else {
            regular = 0d;
            overtime = (end - start) * rate * mult;
        }
        return string.Format("${0:0.00}", regular + overtime + 0.001);
    }
}
```

## Codigo de Prueba :
```cs
using NUnit.Framework;

namespace Tests
{
	[TestFixture]
	public class ChallengeTests
	{
		[Test]
		public void Test1()
			=> Assert.AreEqual("$240.00", Challenge.OverTime(new [] { 9, 17, 30, 1.5 }));
		[Test]
		public void Test2() 
			=> Assert.AreEqual("$400.00", Challenge.OverTime(new double[] { 9, 18, 40, 2 }));
		[Test]
		public void Test3() 
			=> Assert.AreEqual("$325.00", Challenge.OverTime(new [] { 13, 20, 32.5, 2 }));
		[Test]
		public void Test4() 
			=> Assert.AreEqual("$100.00", Challenge.OverTime(new [] { 9, 13, 25, 1.5 }));
		[Test]
		public void Test5() 
			=> Assert.AreEqual("$364.00", Challenge.OverTime(new [] { 11.5, 19, 40, 1.8 }));
		[Test]
		public void Test6() 
			=> Assert.AreEqual("$210.00", Challenge.OverTime(new[] { 10, 17, 30, 1.5 }));
		[Test]
		public void Test7() 
			=> Assert.AreEqual("$209.63", Challenge.OverTime(new [] { 10.5, 17, 32.25, 1.5 }));
		[Test]
		public void Test8() 
			=> Assert.AreEqual("$84.00", Challenge.OverTime(new [] { 16, 18, 30, 1.8 }));
		[Test]
		public void Test9() 
			=> Assert.AreEqual("$130.00", Challenge.OverTime(new [] { 18, 20, 32.5, 2 }));
		[Test]
		public void test10() 
			=> Assert.AreEqual("$52.50", Challenge.OverTime(new [] { 13.25, 15, 30, 1.5 }));
		[Test]
		public void Test11() 
			=> Assert.AreEqual("$432.32", Challenge.OverTime(new [] { 13, 21, 38.6, 1.8 }));
	}
}
```
## Estimacion :
40 minutos

## Actual Duracion :
40 minuto

<hr>

## <u>3. Tercer Ejercicio </u>

### Instrucciones
Create a function that returns the simplified version of a fraction.

### Ejemplos
+ Simplify("4/6") ➞ "2/3"
+ Simplify("10/11") ➞ "10/11"
+ Simplify("100/400") ➞ "1/4"
+ Simplify("8/4") ➞ "2"
### Notes
A fraction is simplified if there are no common factors (except 1) between the numerator and the denominator. For example, 4/6 is not simplified, since 4 and 6 both share 2 as a factor.
If improper fractions can be transformed into integers, do so in your code (see example #4).

## Codigo Realizado :
```cs
using System;
public class Program 
{
		public static string Simplify(string str)
		{
			string[] strArray = str.Split('/');

			int num1 = Convert.ToInt32(strArray[0]);
			int num2 = Convert.ToInt32(strArray[1]);

			for (int i = 2; i < Math.Max(num1,num2); i++)
			{
				if (num1 % i == 0 && num2 % i == 0)
				{
					num1 /= i;
					num2 /= i;
					i = 1;

				}
			}

			return num2 == 1 ? num1.ToString() : 
								string.Concat(num1.ToString(), "/", num2.ToString());

		}
}
```
## Codigo de Prueba :
```cs
using NUnit.Framework;
using System;

[TestFixture]
public class Tests
{
		[Test]
		[TestCase("5/7", Result="5/7")]
		[TestCase("4/6", Result="2/3")]
		[TestCase("11/10", Result="11/10")]
		[TestCase("8/4", Result="2")]
		[TestCase("7/4", Description="should work for improper fractions", Result="7/4")]
		[TestCase("6/4", Result="3/2")]
		[TestCase("300/200", Result="3/2")]
		[TestCase("50/25", Result="2")]
		[TestCase("5/45", Result="1/9")]
    public static string Simplify(string str) 
    {
				Console.WriteLine($"Input: {str}");
        return Program.Simplify(str);
    }
}
```
## Estimacion :
50 minutos

## Actual Duracion :
35 minuto
