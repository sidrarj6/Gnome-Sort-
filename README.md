# Gnome-Sort-
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace ConsoleApplication45
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("\t\t\t\t==========");
            Console.WriteLine("\t\t\t\tGNOME SORT");
            Console.WriteLine("\t\t\t\t==========");
            Console.WriteLine("\t\t\t( Compare , Swap , Repeat )");
            Console.Write("=> Un-Sorted List\n");
            Console.WriteLine("   --------------");
            int[] arrays = new int[7];
            try
            {
                using (StreamReader sr = new StreamReader("C:\\Users\\user\\Desktop\\File.txt"))
                {
                    for (int x = 0; x < 7; x++)
                    {

                        arrays[x] = Convert.ToInt32(sr.ReadLine());

                    }
                    for (int x = 0; x < 7; x++)
                    {
                        Console.Write("\t* ");
                        Console.WriteLine(arrays[x]);

                    }

                }
            }
            catch (Exception e)
            {
                Console.WriteLine("The file could not be found");
                Console.WriteLine(e.Message);
            }

            int[] array = new int[7];
            array = arrays;

            for (int i = 0; i < array.Length; i++)
            {
                while (i < array.Length)
                {
                    if (i == 0 || array[i - 1] <= array[i])
                        i++;
                    else
                    {
                        int tmp = array[i];
                        array[i] = array[i - 1];
                        array[i - 1] = tmp;
                        i -= 1;
                    }
                }
            }
            Console.Write("\n=> After Sorting\n");
            Console.WriteLine("   -------------");
            for (int i = 0; i < array.Length; i++)
            {
                Console.Write("\t* ");
                Console.WriteLine(array[i]);
            }

            for (int y = 0; y < 7; y++)
            {
                int[] lines = array;
            }
            string mydocpath = "C:\\Users\\user\\Desktop\\File.txt";
            using (StreamWriter outputFile = new StreamWriter(mydocpath))
            {
                foreach (int line in array)
                {
                    outputFile.WriteLine(line);
                }

            }
            Console.WriteLine("\n\t\t********** File has been Updated ! **********");
            Console.Read();
        }
    }
}
