c-shasp-program
===============

c#

namespace quiz3
{
    class main
    {
        static void Main(string[] args)
        {
            Triangle T = new Triangle();
            
            while (true)
            {
                Console.WriteLine("請輸入第一點x座標:");
                T.x1 = double.Parse(Console.ReadLine());
                Console.WriteLine("請輸入第一點y座標:");
                T.y1 = double.Parse(Console.ReadLine());

                Console.WriteLine("請輸入第二點x座標:");
                T.x2 = double.Parse(Console.ReadLine());
                Console.WriteLine("請輸入第二點y座標:");
                T.y2 = double.Parse(Console.ReadLine());

                Console.WriteLine("請輸入第三點x座標:");
                T.x3 = double.Parse(Console.ReadLine());
                Console.WriteLine("請輸入第三點y座標:");
                T.y3 = double.Parse(Console.ReadLine());

                if (!T.isValid())
                {
                    Console.WriteLine("三角形不合法!");
                    Console.WriteLine("請重新輸入!");
                    continue;
                }

                Console.WriteLine("周長= {0}", T.Perimeter());
                Console.WriteLine("面積= {0}", T.Area());
                Console.WriteLine("外接圓半徑= {0}", T.RadiusOfCircumcircle());

                if (T.isRight())
                {
                    Console.WriteLine("這是一個直角三角形!");
                }
                else
                {
                    Console.WriteLine("這不是一個直角三角形!");
                }

                Console.WriteLine("Again?");

                string select = Console.ReadLine().ToUpper(); //fool-proofing
                
                if ("Y" != select)
                {
                    Console.WriteLine("Program end!");
                    Console.Read();
                    break;
                }
            }
        }
    }
}
