using System;
using System.Threading;

class MainClass {
    static int currentPosition = 1;

    public static void Main(string[] args) {
        Timer rocketTimer = new Timer(MoveRocket, null, 0, 1000); // Καλεί την MoveRocket κάθε 1000 milliseconds (1 δευτερόλεπτο)
        Console.ReadKey(); // Περιμένει για το πάτημα ενός κουμπιού προτού τερματίσει το πρόγραμμα
    }

    static void MoveRocket(object state) {
        Console.Clear(); // Καθαρίζει την οθόνη

        string v = @"
                                   /\
                                  /  \
                                 |    |
                                 |    |
                                 |    |
                                 |    |
                                 |    |
                                 |    |
                                 |    |
                                 |    |
                                /____\
                                ******
                                ******
                                ******
        ";

        string g = @"
                                /\
                               /  \
                              |    |
                              |    |
                              |    |
                              |    |
                              |    |
                              |    |
                              |    |
                              /____\
                              ******
                              ******
                              ******
        ";

        if (currentPosition <= 10) {
            Console.WriteLine(new string('\n', currentPosition - 1)); // Κενό πριν τον πυραύλο
            Console.WriteLine(v);
            Console.WriteLine(g);
            currentPosition++;
        }
        else {
            currentPosition = 1; // Επαναφορά της θέσης για τον επόμενο κύκλο
        }
    }
}
