using System;
using System.Diagnostics;

class Program
{
    static void Main()
    {
        Stopwatch timer = new Stopwatch();

        Console.WriteLine("hold S to Start/Stop, R to Reset, Q to Quit");

        while (true)
        {
            if (Console.KeyAvailable)
            {
                var key = Console.ReadKey(true).Key;

                if (key == ConsoleKey.S)
                {
                    if (timer.IsRunning)
                        timer.Stop();
                    else
                        timer.Start();
                }
                else if (key == ConsoleKey.R)
                {
                    timer.Reset();
                }
                else if (key == ConsoleKey.Q)
                {
                    break;
                }
            }

            Console.Clear();
            Console.WriteLine("Time: " + timer.Elapsed.ToString(@"hh\:mm\:ss\.fff"));
        }
    }
}

state("Bonelab")
{
    // Example: a variable you could track
    int dummy : 0x000000; 
}

start
{
    return false; // change later when you add a real condition
}

split
{
    return false; // same here
}

reset
{
    return false;
}
