# My_Calculator
This is my first project in C# which i'm currently learning about in school. Note that it's in danish. Any comments on what i can improve/add is greatly apreciated.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Linq.Expressions;
using System.Text;
using System.Threading.Tasks;

namespace Lommeregner_intro
{
    internal class Program
    {
        

        static void Main(string[] args)
        {
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine("En meget god lommeregner.exe");
            Console.ResetColor();
            Boolean stop = false;
            while (!stop)
            // while (true) gør at programmet kører indtil den får en false.
            {
                try
            {


                    Console.Write("Indsæt første tal: ");
                    string input1 = Console.ReadLine();
                    //ovenover har jeg readline til input1/det første tal

                    Console.Write("Indsæt næste tal: ");
                    string input2 = Console.ReadLine();
                    //ovenover har jeg readline til input2/det andet tal

                    double nummer1 = Convert.ToDouble(input1);
                    double nummer2 = Convert.ToDouble(input2);
                    //ovenover bliver input 1 og 2 konverteret til doubles/decimaltal, det betyder bare at programmet så også kan beregne decimaltal.

                    Console.WriteLine("vælg en operation +,-,* og /");
                    char operation = Console.ReadLine()[0];
                    double sum = 0;
                    //ovenover er starten på min switch-statement, som vi kan se indenunder writeline har switchen 4 operationer.


                    switch (operation)
                    //ovenover har jeg brugt en switch-statement til at lave de 4 forskellige operationer mit program skal kunne. 
                    {

                        case '+':
                            sum = nummer1 + nummer2;
                            break;
                        case '-':
                            sum = nummer1 - nummer2;
                            break;
                        case '*':
                            sum = nummer1 * nummer2;
                            break;
                        case '/':
                            sum = nummer1 / nummer2;
                            break;
                        //ovenover har jeg mine cases, de styrer hvad der sker med bruger inputet baseret på hvilken operatør man har brugt i programmet.
                        default:
                            Console.WriteLine("vælg en rigtig operatør");
                            break;
                            //default betyder at hvis man ikke har brugt en case så vil programmet gøre det der står inden under default,
                            //hvilket i dette tilfælde vil den skrive "vælg en rigtig operatør"


                    }



                    Console.ForegroundColor = ConsoleColor.Green;
                    Console.WriteLine("dit resultat er: " + sum);
                    //ovenover har jeg en writeline som skriver summen i grøn farve for at resultatet bliver mere synligt. 
                    Console.ResetColor();
                    //Efter programmet har vist resultatet bliver farven nulstillet

                    if (sum < 0)
                        Console.WriteLine("Er du sikker på at du har skrevet tallene i den rigtige rækkefølge?.");
                    //ovenover har jeg en if-statement som har en writeline der bliver udløst hvis summen er mindre end 0.
                    else
                        Console.WriteLine("Du har sikkert skrevet tallene i den rigtige rækkefølge.");
                    //ovenover har jeg en else-statement som bliver udløst hvis summen er større end eller = 0.

                    {
                        Console.WriteLine("Vil du fortsætte indtast 'b', vil du stoppe indtast 'a'");
                        //ovenover har jeg starten på en metode til om man vil fortsætte programmet eller stoppe programmet.
                        
                        char input = Console.ReadLine()[0];
                        if (input == 'a')
                        {
                            stop=true;
                            Console.ForegroundColor = ConsoleColor.Red;
                            Console.WriteLine("Lukker nu for En meget god lommeregner.exe");
                            Console.ResetColor();
                        }
                        //ovenover har jeg min første if-statement, hvor at hvis input = 'a' så vil programmet slukke.

                        if (input == 'b')
                        {
                            Console.WriteLine("Programmet fortsætter......");
                            Console.WriteLine("Tryk på enter");
                        }
                        //ovenover har jeg min næste if-statement, hvor at hvis input = 'b' så vil programmet fortsætte.

                    


                    }


                }

                catch (Exception e) { Console.WriteLine(e.Message + " Tryk på enter for at fortsætte"); }
                //ovenover har jeg en catch-statement som fanger en fejl i stedet for at crashe. Fx hvis man skriver et bogstav i stedet for et tal,
                //så vil programmet skrive hvad end fejlen er.
                Console.ReadLine();


            }
            


        }


            




        }
        }
  



