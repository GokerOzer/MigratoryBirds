   [HackerRank Migratory Birds](https://www.hackerrank.com/challenges/migratory-birds/problem)
    
    
    
    using System.CodeDom.Compiler;
    using System.Collections.Generic;
    using System.Collections;
    using System.ComponentModel;
    using System.Diagnostics.CodeAnalysis;
    using System.Globalization;
    using System.IO;
    using System.Linq;
    using System.Reflection;
    using System.Runtime.Serialization;
    using System.Text.RegularExpressions;
    using System.Text;
    using System;

    class Result
    {
       

    public static int migratoryBirds(List<int> arr)
    {
        
        int counter1 = 0, counter2 = 0, counter3 = 0, counter4 = 0, counter5 = 0;


        for (int i = 0; i < arr.Count; i++)
        {
            int eslenik = arr[i];
            switch (eslenik)
            {
                case 1:
                    counter1++;
                    break;
                case 2:
                    counter2++;
                    break;
                case 3:
                    counter3++;
                    break;
                case 4:
                    counter4++;
                    break;
                case 5:
                    counter5++;
                    break;
            }
        }
        int[] countHolder = { counter1, counter2, counter3, counter4, counter5 };
        int mostFrequent = 0;
        int smallestMostFrequent = 0;

              


        for (int i = 0; i < countHolder.Length ; i++)
        {
            if (countHolder[i] >mostFrequent)
                mostFrequent = countHolder[i];            
        }

        for (int i = countHolder.Length - 1; i >= 0; i--)
        {
            if (countHolder[i] == mostFrequent)
                smallestMostFrequent = i + 1;
        }

        return smallestMostFrequent;

    }

    }

    class Solution
    {
        public static void Main(string[] args)
        {
       
        int arrCount = Convert.ToInt32(Console.ReadLine().Trim());

        List<int> arr = Console.ReadLine().TrimEnd().Split(' ').ToList().Select(arrTemp => Convert.ToInt32(arrTemp)).ToList();

        int result = Result.migratoryBirds(arr);

        Console.WriteLine(result);
        Console.ReadLine();

        
    }
    }
