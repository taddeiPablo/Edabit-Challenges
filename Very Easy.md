
# Very Easy


## Ejercicios Realizados :

1. Primer Ejercicio
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

public class Program 
{
    public static int CalcAge(int age) 
    {
			return age * 365;
    }
}

## Codigo de Prueba :
[TestFixture]
public class Tests {
	[Test]
	[TestCase(10, Result=3650)]
	[TestCase(0, Result=0)]
	[TestCase(73, Result=26645)]
	public static int CalcAge(int age)
	{
		Console.WriteLine($"Input: {age}");
		return Program.CalcAge(age);
	}
}

## Estimacion :
2 minutos

## Actual Duracion :
1 minuto




