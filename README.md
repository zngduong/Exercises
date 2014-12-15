using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
public class Card
    {
        public string Rank { get; set; }
        public string Suit { get; set; }
    }
    class Program
    {
        static private string[] Ranks = {"A","2","3","4","5","6","7","8","9","10","J","Q","K"};
        static private string[] Suits = { "bich", "chuon", "ro", "co" };
        static private List<Card> DeckFull = new List<Card>();
        static void Main(string[] args)
        {
            foreach (string r in Ranks)
            {
                foreach (string s in Suits)
                {
                    DeckFull.Add(new Card() { Rank = r, Suit = s });
                }
            }
            List<Card> result = new List<Card>();
            Random rand = new Random();
            int i = 0;
            while (i <= 12)
			{
                int num = rand.Next(1, 52);
                while (DeckFull[num] != null)
                {
                    result.Add(DeckFull[num]);
                    DeckFull[num] = null;
                    i++;
                }
			}
            Console.WriteLine("Random deck cards:");
            foreach (var item in result)
            {
                Console.WriteLine("Card: {0},{1}",item.Rank,item.Suit);
            }
            Console.ReadKey();
        }

        
    }
