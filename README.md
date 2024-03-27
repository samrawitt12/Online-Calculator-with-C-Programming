# Online-Calculator-with-C-Programming
using System;

class MainClass {
    public static string SimpleOnlineCalculator(string str) {
        // Split the input string into number1, operation, and number2
        string[] parts = str.Split(' ');
        double num1 = double.Parse(parts[0]);
        double num2 = double.Parse(parts[2]);
        char operation = parts[1][0];

        // Perform the arithmetic operation based on the operator
        double result = 0;
        switch (operation) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 == 0) {
                    throw new DivideByZeroException("Cannot divide by zero");
                }
                result = num1 / num2;
                break;
            default:
                throw new ArgumentException("Invalid operation. Please enter one of the following operations: +, -, *, /");
        }

        // Return the result as a string
        return result.ToString();
    }

    static void Main() {
        // Keep this function call here
        Console.WriteLine(SimpleOnlineCalculator(Console.ReadLine()));
    }
}
