\*
First Demo 
Created this little demo console application that spits out hello world with in a console That starts off with a background color of white and then the text color in black. The console then spits out, hello world. The console then ask the user for a color that they would like to change the font to.  And then saves the user response and if the user responds has a space contained within it, it Enters the if statement and removes the space. 
\*

public class Program
 {
     static void Main(string[] args)
     {            
            string txtColorChoose; 
            string UserResponse;

            Console.ForegroundColor = ConsoleColor.Black;
            Console.BackgroundColor = ConsoleColor.White;
            Console.Clear();
            
            Console.WriteLine("Hello World\n\n");

            Console.WriteLine("Enter your favorite color\nYour Options are (Blue, Black, Cyan, Dark Blue, Dark Cyan, Dark Gray, Dark Green, Dark Magenta, Dark Red, Dark Yellow, \nGray, Green, Magenta, Red, White, Yellow): ");
            UserResponse = Console.ReadLine();
            
            txtColorChoose = UserResponse;
            
            if (UserResponse.Contains(' '))
            { 
                UserResponse = UserResponse.Remove(UserResponse.IndexOf(' '), 1);
            }
       
   
            
            
            // Convert the string to ConsoleColor
                
            if (Enum.TryParse(UserResponse, true, out ConsoleColor color))
                {
                    Console.ForegroundColor = color;
                    Console.WriteLine($"\n\nThis text is in the color specified by the user, which was {txtColorChoose}.");
                    
                    //Console.ResetColor();
                }
                else
                {
                    Console.WriteLine("Invalid color name.");
                }
}
}

