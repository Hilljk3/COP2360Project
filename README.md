using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Enter two numbers to divide:");
        Console.Write("Number 1: ");
        string input1 = Console.ReadLine();
        Console.Write("Number 2: ");
        string input2 = Console.ReadLine();

        DivideAndPrintResult(input1, input2);

        Console.WriteLine("\nPress any key to exit.");
        Console.ReadKey();
    }

    static void DivideAndPrintResult(string num1Str, string num2Str)
    {
        try
        {
            // Convert the input strings to integers
            int num1 = int.Parse(num1Str);
            int num2 = int.Parse(num2Str);

            // Perform division
            int result = num1 / num2;

            // Print the result
            Console.WriteLine($"Result of {num1} / {num2} = {result}");
        }
        catch (FormatException)
        {
            Console.WriteLine("Error: Please enter valid integers for division.");
        }
        catch (DivideByZeroException)
        {
            Console.WriteLine("Error: Division by zero is not allowed.");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"An error occurred: {ex.Message}");
        }
    }
}
