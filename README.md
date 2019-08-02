# proiect1
//first repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace incercare
{
    class Program
    {

        private static void align_msg(string s, char color)
        {
            int Width = Console.WindowWidth;
            int nr = (Width - s.Length) / 2;
            for (int i = 0; i < nr; i++)
                Console.Write(" ");
            switch (color)
            {
                case 'b':
                    Console.ForegroundColor = ConsoleColor.Blue;
                    break;
                case 'c':
                    Console.ForegroundColor = ConsoleColor.Cyan;
                    break;
                case 'r':
                    Console.ForegroundColor = ConsoleColor.Red;
                    break;
                case 'y':
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    break;

            }
            Console.Write(s);


        }


        private static void WelcomeScreen()
            {
                int Height = Console.WindowHeight;
                Console.WriteLine();
                Console.WriteLine();
                align_msg(" WELCOME TO RentC ! ", 'c');
                Console.WriteLine();
                Console.WriteLine();
                Console.WriteLine();
                align_msg(" We offer new and easy solutions to manage and control yout company's data without missing anything.", 'b');
                for (int i = 0; i < Height - 8; i++)
                    Console.WriteLine();
                align_msg(" Press ENTER to continue or ESC to quit.", 'b');

                ConsoleKeyInfo keyPressed;
                bool valid = false;
                bool enter = false;
                do
                {
                    keyPressed = Console.ReadKey();
                    if (keyPressed.Key == ConsoleKey.Enter)
                    {
                        valid = true;
                        enter = true;
                    }
                    if (keyPressed.Key == ConsoleKey.Escape)
                    {
                        valid = true;
                    }

                } while (valid == false);
                Console.Clear();

                if (enter == true)
                    menu();

            }


        static void menu()
        {
            align_msg("MENU", 'r');
            Console.WriteLine();
            Console.WriteLine();
            align_msg("Make a choice by pressing a number.",'b');
            Console.WriteLine();
            Console.WriteLine();
            Console.WriteLine("1. Register new car rent");
            Console.WriteLine("2. Update car rent");
            Console.WriteLine("3. List rents");
            Console.WriteLine("4. List available cars");
            Console.WriteLine("5. Register new customer");
            Console.WriteLine("6. Update customer");
            Console.WriteLine("7. List customers");
            Console.WriteLine("8. Quit");

            bool valid = false;
            ConsoleKeyInfo keyPressed;
            do
            {
                keyPressed = Console.ReadKey();
                switch (keyPressed.Key)
                {

                    case ConsoleKey.D1 :
                        valid = true;
                        Console.Clear();
                        Register_new_car_rent();
                        break;

                    case ConsoleKey.D2:
                        valid = true;
                        Console.Clear();
                        Update_car_rent();
                        break;

                    case ConsoleKey.D3:
                        valid = true;
                        Console.Clear();
                        List_rents();
                        break;

                    case ConsoleKey.D4:
                        valid = true;
                        Console.Clear();
                        List_available_cars();
                        break;

                    case ConsoleKey.D5:
                        valid = true;
                        Console.Clear();
                        Register_new_customer();
                        break;

                    case ConsoleKey.D6:
                        valid = true;
                        Console.Clear();
                        Update_customer();
                        break;

                    case ConsoleKey.D7:
                        valid = true;
                        Console.Clear();
                        break;

                }
                

            } while (valid == false);

        }

        private static void List_rents()
        {
            throw new NotImplementedException();
        }

        private static void Update_car_rent()
        {
            throw new NotImplementedException();
        }

        private static void Register_new_car_rent()
        {
            Console.WriteLine("Please insert the data necessary to register a new car. ");
            Console.WriteLine("After you completed a fiels press enter.");
            Console.WriteLine();
            Console.WriteLine();
            Console.Write("     Car Palte  ");
            string car_plate = Console.ReadLine();
            Console.WriteLine();
            Console.Write("     Client ID  ");
            string ID = Console.ReadLine();
            Console.WriteLine();
            Console.Write("     Start Date (ex: Jan 1, 2009) ");
            string st_date = Console.ReadLine();
            Console.WriteLine();
            Console.Write("     End Date   ");
            string end_date = Console.ReadLine();
            Console.WriteLine();
            Console.Write("     City       ");
            string city = Console.ReadLine();

            /* if (Car_model_available(car_plate) && ID_exists(ID) && car_available_city(car_plate, city) && correct_date(st_date, end_date))
             {
               //  save_to_data_base();
                 Console.Clear();
                // menu();
             }
             else
             {
                 Console.Clear();
                 Console.WriteLine("You introduced some incompatible data. ");
                 //esc vs enter
             }*/
        }
        private static bool correct_date(string st_date, string end_date)
        {
            DateTime start = DateTime.Parse(st_date);
            DateTime end = DateTime.Parse(end_date);
            if (DateTime.Compare(start, end) <= 0)
                return true;
            return false;
        }

        private static void List_available_cars()
        {
            throw new NotImplementedException();
        }

        private static void Register_new_customer()
        {
            throw new NotImplementedException();
        }

        private static void Update_customer()
        {
            throw new NotImplementedException();
        }

        static void Main(string[] args)
            {
                WelcomeScreen();
            }

        }
    }
