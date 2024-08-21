
List<double> numbers = new List<double>();


const string triggerWord = "calculate";

Console.WriteLine("Enter numbers to add to the list. Type 'calculate' to calculate the average.");

while (true)
{
    Console.Write("Enter a number (or type 'calculate' to finish): ");
    string input = Console.ReadLine()?.Trim();

    if (input?.ToLower() == triggerWord)
    {
        break; 
    }

    if (double.TryParse(input, out double number))
    {
        numbers.Add(number); 
    }
    else
    {
        Console.WriteLine("Please enter a valid number.");
    }
}

if (numbers.Count > 0)
{
   
    double sum = 0;
    foreach (var number in numbers)
    {
        sum += number;
    }
    double average = sum / numbers.Count;

  
    Console.WriteLine($"The average is: {average:F4}");
}
else
{
    Console.WriteLine("No numbers were entered.");
}
