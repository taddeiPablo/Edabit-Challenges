
# Hard


## Ejercicios Realizados :

## <u>1. Primer Ejercicio</u>
### Next Prime
Given an integer, create a function that returns the next prime. If the number is prime, return the number itself. https://edabit.com/challenge/2QvnWexKoLfcJkSsc

### Instrucciones
Given an integer, create a function that returns the next prime. If the number is prime, return the number itself.

### Ejemplos
+ NextPrime(12) ➞ 13
+ NextPrime(24) ➞ 29
+ NextPrime(11) ➞ 11
// 11 is a prime, so we return the number itself.

### Notas
+ N/A

## Codigo Realizado :
```cs
public class Program 
{
    public static int NextPrime(int num) 
    {
			int result = 0;
			for(int i = 2; i < num/2; i++)
			{
				if(num % i == 0){
					result = NextPrime(num+1);
					break;
				}else{
					result = num;
				}
			}
			return result;
    }
}
```

## Codigo de Prueba :
```cs
	[Test]
		[TestCase(12, Result=13)]
		[TestCase(24, Result=29)]
		[TestCase(11, Result=11)]
		[TestCase(13, Result=13)]
		[TestCase(14, Result=17)]
		[TestCase(33, Result=37)]
    public static int NextPrime(int num) 
    {
				Console.WriteLine($"Input: {num}");
        return Program.NextPrime(num);
    }
```
## Estimacion :
8 minutos

## Actual Duracion :
6 minuto

<hr>

## <u>2. Segundo Ejercicio </u>
### Find the Vertex of a Quadratic
Find the Vertex of a Quadratic. https://edabit.com/challenge/TH8Y97XYtGgbDW8Qw

### Instrucciones
Every quadratic curve y = a x² + b x + c has a vertex point: the turning point where the curve stops heading down and starts going up.
Given the values a, b and c, you need to return the coordinates of the vertex. Return your answers rounded to 2 decimal places.

### Ejemplos
+ FindVertex(1, 0, 25)  ➞ [0, 25]
// The vertex of y=x²+25 is at (0, 25).
+ FindVertex(-1, 0, 25) ➞ [0, 25]
// The vertex of y=-x²+25 is at (0, 25).
+ FindVertex(1, 10, 4) ➞ [-5, -21]
// The vertex of y=x²+10x+4 is at (-5, -21).

### Notas
+ See Resources if you're not sure how to find the x or y coordinates of the vertex.
+ a will always be non-zero.

## Codigo Realizado :
```cs
using System;

public class Program {
	public static double[] FindVertex(int a, int b, int c) {
		double x = -b / (2d * a);
		double y = a * Math.Pow(x,2) + (b * x) + c;
		double[] result = new double[2];
		result[0] = Math.Round(x,2);
		result[1] = Math.Round(y,2);
		return result;
	}
}
```

## Codigo de Prueba :
```cs
[TestCase(-1, 0, 25, Result = new double[] {0, 25d})]
	[TestCase(1, 10, 25, Result = new double[] {-5d, 0d})]
	[TestCase(8, 4, 0, Result = new double[] {-0.25d, -0.5d})]
	[TestCase(4, -200, 1000, Result = new double[] {25d, -1500d})]
	[TestCase(1, -50, -1000, Result = new double[] {25d, -1625d})]
	[TestCase(-1, 20, 600, Result = new double[] {10d, 700d})]
	[TestCase(5, 1, 20, Result = new double[] {-0.1d, 19.95d})]
	public static double[] FixedTest(int a, int b, int c) => 
		Program.FindVertex(a, b, c);
```
## Estimacion :
8 minutos

## Actual Duracion :
6 minuto

<hr>

## <u>3. Tercer Ejercicio </u>
### Meme Sum :)
For this challenge, forget how to add two numbers together. The best explanation on what to do for this function is this meme:
. https://edabit.com/challenge/6APNLL9DAKzsHJfCn

### Instrucciones
For this challenge, forget how to add two numbers together. The best explanation on what to do for this function is this meme.

### Ejemplos
+ MemeSum(26, 39) ➞ 515
// 2+3 = 5, 6+9 = 15
// 26 + 39 = 515
+ MemeSum(122, 81) ➞ 1103
// 1+0 = 1, 2+8 = 10, 2+1 = 3
// 122 + 81 = 1103
+ MemeSum(1222, 30277) ➞ 31499

### Notas
+ N/A

## Codigo Realizado :
```cs
public class Program 
{
    public static int MemeSum(int a, int b) 
    {
			string aStr = a.ToString();
			string bStr = b.ToString();
			
			string result ="";
			if(aStr.Length > bStr.Length)
			{
				for(int i=0; i<aStr.Length - bStr.Length; i++){
					bStr = bStr.Insert(0, "0");
				}
			}else if(aStr.Length < bStr.Length){
				for(int i=0; i<bStr.Length - aStr.Length; i++){
					aStr = aStr.Insert(0, "0");
				}
			}
			for(int j = 0; j<aStr.Length; j++)
			{
				int temp = int.Parse(aStr[j].ToString()) + int.Parse(bStr[j].ToString());
				result += temp.ToString();
			}
			return int.Parse(result);
    }
}
```

## Codigo de Prueba :
```cs
[Test]
[TestCase(2, 11, Result=13)]
[TestCase(0, 1, Result=1)]
[TestCase(0, 0, Result=0)]
[TestCase(16, 18, Result=214)]
[TestCase(26, 39, Result=515)]
[TestCase(122, 81, Result=1103)]
[TestCase(1222, 30277, Result=31499)]
[TestCase(38810, 1383, Result=391193)]
[TestCase(1236, 30977, Result=31111013)]
[TestCase(49999, 49999, Result=818181818)]
	
	public static int MemeSum(int a, int b)
	{
		Console.WriteLine($"Input: {a} {b}");
		return Program.MemeSum(a, b);
	}
```
## Estimacion :
10 minutos

## Actual Duracion :
8 minuto
