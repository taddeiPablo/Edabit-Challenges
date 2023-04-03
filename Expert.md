
# Expert


## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>
### Array of Multiples
Create a function that takes two numbers as arguments (num, length) and returns an array of multiples of num until the array length reaches length. https://edabit.com/challenge/2QvnWexKoLfcJkSsc

### Instrucciones
Create a function that counts how many n-digit numbers have the same sum of the first half and second half of the digits (“lucky” numbers). The number n is even. For example, for n = 6, the numbers "001010", "112220", "000000" are lucky.

### Ejemplos
+ LuckyTicket(2) ➞ 10
+ LuckyTicket(4) ➞ 670
+ LuckyTicket(12) ➞ 39581170420
### Notas
+ There are checks for n > 10, so watch out for code performance.
If you have problems finding a productive algorithm, look in the comments, there is one good person who explained the solution algorithm.

+ NOTA : Para resolver este ejercicio tuve que mirar la informacion de ayuda ya que la explicacion del mismo no era muy clara y generaba confusion.
## Codigo Realizado :
```cs
using System;
public class Program
{
    public static long LuckyTicket(int n)
        {
            long count = 0;
            for (int i = (n / 2) * 9; i >= 0; i--)
            {
                count += (long)Math.Pow(Sum(i, n / 2, 0), 2);
            }
            return count;
        }
	
        public static long Sum(int num, int digits, int input)
        {
            long count = 0;
            for (int i = 0; i < 10; i++)
            {
                if (digits == 1 && i + input == num)
                {
                    count++;
                }
                else if (digits != 1)
                {
                    count += Sum(num, digits - 1, i+input);
                }
            }
            return count;
        }
}
```

## Codigo de Prueba :
```cs
using NUnit.Framework;
[TestFixture]
public class Tests
{
  [Test]
		[TestCase(2,Result=10)]
		[TestCase(4,Result=670)]
		[TestCase(6,Result=55252)]
		[TestCase(8,Result=4816030)]
		[TestCase(10,Result=432457640)]
		[TestCase(12,Result=39581170420)]
		[TestCase(14,Result=3671331273480)]
  public static double FixedTest(int n)
    {
        return Program.LuckyTicket(n);
    }
}
```
## Estimacion :
40 minutos

## Actual Duracion :
35 minuto

<hr>

## <u>2. Segundo Ejercicio </u>

### Instrucciones
Write a function that returns all sets of three elements that sum to 0.

### Ejemplos
+ ThreeSum(new int[] { 0, 1, -1, -1, 2 }) ➞ { { 0, 1, -1 }, { -1, -1, 2 } }
+ ThreeSum(new int[] { 0, 0, 0, 5, -5 }) ➞ { { 0, 0, 0 }, { 0, 5, -5 } }
+ ThreeSum(new int[] { 1, 2, 3 }) ➞ { }
+ ThreeSum(new int[1]) ➞ { }

### Notas
The original array may contain duplicate numbers.
Each three-element subarray in your output should be distinct.
Subarrays should be ordered by the first element of the subarray.
Subarrays themselves should be ordered the same as the original array.
Return an empty array if no three elements sum to zero.
Return an empty array if there are fewer than three elements.

## Codigo Realizado :
```cs
using System.Collections.Generic;
public class Program
{
	public static List<int[]> ThreeSum(int[] arr)
	{
		HashSet<string> alreadyInResult = new HashSet<string>();
		List<int[]> result = new List<int[]>();

		for (int i = 0; i < arr.Length - 2; i++)
		{
			for (int j = i + 1; j < arr.Length - 1; j++)
			{
				for (int k = j + 1; k < arr.Length; k++)
				{
					//HashSet.Add return a bool, true if can add the element
					if (arr[i] + arr[j] + arr[k] == 0 && alreadyInResult.Add(arr[i] + "|" + arr[j] + "|" + arr[k]))
						result.Add(new int[] { arr[i], arr[j], arr[k] });
				}
			}
		}

		return result;
	}
}
```

## Codigo de Prueba :
```cs
using NUnit.Framework;
using System;
using System.Linq;

[TestFixture]
public class Tests
{
    [TestCase(new int[] { 0, 1, -1, -1, 2 }, Result = "{ { 0, 1, -1 }, { -1, -1, 2 } }")]
    [TestCase(new int[] { 0, 0, 0, 5, -5 }, Result = "{ { 0, 0, 0 }, { 0, 5, -5 } }")]
    [TestCase(new int[] { 0, -1, 1, 0, -1, 1 }, Result = "{ { 0, -1, 1 }, { 0, 1, -1 }, { -1, 1, 0 }, { -1, 0, 1 }, { 1, 0, -1 } }")]
    [TestCase(new int[] { 0, 5, 5, 0, 0 }, Result = "{ { 0, 0, 0 } }")]
    [TestCase(new int[] { 0, 5, -5, 0, 0 }, Result = "{ { 0, 5, -5 }, { 0, 0, 0 }, { 5, -5, 0 } }")]
    [TestCase(new int[] { 1, 2, 3, -5, 8, 9, -9, 0 }, Result = "{ { 1, 8, -9 }, { 2, 3, -5 }, { 9, -9, 0 } }")]
    [TestCase(new int[] { 0, 0, 0 }, Result = "{ { 0, 0, 0 } }")]
    [TestCase(new int[] { 1, 5, 5, 2 }, Result = "{  }")]
    [TestCase(new int[] { 1, 1 }, Result = "{  }")]
    [TestCase(new int[] { }, Result = "{  }")]
    public static string TestThreeSum(int[] arr)
    {
        var res = Program.ThreeSum(arr);
        var result = string.Join(", ", res.Select(itm => $"{{ {itm[0]}, {itm[1]}, {itm[2]} }}"));
        return "{ " + result + " }";
    }
}
```
## Estimacion :
50 minutos

## Actual Duracion :
40 minuto

<hr>

## <u>3. Tercer Ejercicio </u>

### Instrucciones
Create a function that takes four integer arrays of 2 elements. The first three are (x, y) coordinates of three corners of a triangle. Return True if the fourth array — the (x, y) coordinates of a test point — lies within the triangle, False if it doesn't.

### Ejemplos
+ WithinTriangle((1, 4), (5, 6), (6, 1), (4, 5)) ➞ True
+ WithinTriangle((1, 4), (5, 6), (6, 1), (3, 2)) ➞ False
+ WithinTriangle((-6, 2), (-2, -2), (8, 4), (4, 2)) ➞ True

## Codigo Realizado :
```cs
using System;
public class Program
{
	    public static bool WithinTriangle(int[] p1, int[] p2, int[] p3, int[] test)
        {
						//Se calcula el area de 3 triangulos distintos
						//formados por p1,p2,p3, y otros 2 que serian parciales de estos
						//con el punto test
						//Si las areas resultantes son iguales, entonces esta dentro
						
            return (Area(p1, p2, test) + Area(p1, p3, test) + Area(p3, p2, test)) == Area(p1, p2, p3);
        }
        static double Area(int[] p1, int[] p2, int[] test)
        {
					//Regla de cramer 
            return Math.Abs((p2[0] - p1[0]) * (test[1] - p1[1]) - (test[0] - p1[0]) * (p2[1] - p1[1])) / 2;
        }
}
```
## Codigo de Prueba :
```cs
using NUnit.Framework;
using System;
using System.Linq;
[TestFixture]
public class Tests
{
    [TestCase(new int[] { 1, 4 }, new int[] { 5, 6 }, new int[] { 6, 1 }, new int[] { 4, 5 }, Result = true)]
    [TestCase(new int[] { 1, 4 }, new int[] { 5, 6 }, new int[] { 6, 1 }, new int[] { 3, 2 }, Result = false)]
    [TestCase(new int[] { 1, 7 }, new int[] { 2, 4 }, new int[] { 9, 3 }, new int[] { 2, 6 }, Result = true)]
    [TestCase(new int[] { 1, 7 }, new int[] { 2, 4 }, new int[] { 9, 3 }, new int[] { 6, 5 }, Result = false)]
    [TestCase(new int[] { -2, 6 }, new int[] { 12, -3 }, new int[] { 1, 7 }, new int[] { 9, -1 }, Result = true)]
    [TestCase(new int[] { -2, 6 }, new int[] { 12, -3 }, new int[] { 1, 7 }, new int[] { 4, 2 }, Result = false)]
    [TestCase(new int[] { -6, 2 }, new int[] { -2, -2 }, new int[] { 8, 4 }, new int[] { 4, 2 }, Result = true)]
    [TestCase(new int[] { -6, 2 }, new int[] { -2, -2 }, new int[] { 8, 4 }, new int[] { 0, -4 }, Result = false)]    
    public static bool TestWithinTriangle(int[] p1, int[] p2, int[] p3, int[] test)
    {
        Console.WriteLine($"Input: ({p1[0]},{p1[1]}), ({p2[0]},{p2[1]}), ({p3[0]},{p3[1]}), ({test[0]},{test[1]})");
        return Program.WithinTriangle(p1, p2, p3, test);
    }
}
```
## Estimacion :
50 minutos

## Actual Duracion :
50 minuto
