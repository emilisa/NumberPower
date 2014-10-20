NumberPower
===========

For cycle that replaces Math.Pow() for any given number, aslo includes Timer.

using System;
using System.Numerics;
using System.Collections.Generic;

class NumberPower

{
    static void Main()
    
    {
        while (true)
        {
            Stopwatch stopWatch = new Stopwatch();
                        
            Console.BufferWidth = 120;
            
            List<BigInteger> poweredNumbers = new List<BigInteger> { };   
            
            Console.WriteLine("Type number to power:");
            Console.ForegroundColor = ConsoleColor.Yellow;
            int numberToPow = int.Parse(Console.ReadLine());
            Console.ResetColor();

            Console.WriteLine("Type power:");
            Console.ForegroundColor = ConsoleColor.Yellow;
            int powValue = int.Parse(Console.ReadLine());
            Console.ResetColor();
            
            stopWatch.Start();

            BigInteger result = 1;

            for (int x = 0; x < powValue; x++)
            {
                result *= numberToPow;

                poweredNumbers.Add(result);
            }

            Console.WriteLine("Number {0} powered with {1} is:", numberToPow, powValue);
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine(result);
            Console.ResetColor();
            Console.Write("\n");

            int a = 1;
            foreach (var item in poweredNumbers)
            {
                Console.WriteLine("Number {0} powered with {1} is {2} ",numberToPow, a++, item);
            }

            stopWatch.Stop();
            TimeSpan timeElapsed = stopWatch.Elapsed;
            
            Console.Write("\n");
            Console.WriteLine(timeElapsed);
        }
    }
}
