# Birthday
This program is talking your date of birth as input and tells the day of week on which you born.

package special;
import java.util.Scanner;
public class Birthday {
	static int d,m,y,c,l; 
	public static void main(String[] args) 
	{		
			Scanner sc = new Scanner(System.in);
				
					System.out.println("Hii friends");
					System.out.println("I will tell you the day on which you born.");
					System.out.println("Please provide date, month No. and year saperately");
					System.out.print("Only enter the date: ");
					d= sc.nextInt(); 
									//d = date 
					if(d>31 || d<=0){ 
						System.out.println("invalid date");
						System.exit(0);}
					
					System.out.print("Enter the month No.: ");
					m= sc.nextInt();
					
					if(m>12 || m<=0){
						System.out.println("invalid month");
						System.exit(0);}
					else if( m == 4 || m == 6 || m == 9 || m == 11) // These months dont have No. of days more than 30 
					{
							if(d>30){
								System.out.println("invalid date");
								System.exit(0);}	}
			
					else if(m==2) // Feb month
					{
						if(d>29)
							{System.out.println("invalid date");
							System.exit(0);}
					}
					System.out.print("Enter the Year: " );
					y= sc.nextInt();
					if(y<=0)
					{System.out.println("invalid year");
							System.exit(0);}
					if (y%4==0)  
					{
						if(y%100==0)  // If century month
						{
							if(y%400 == 0) // If divisible by 100, it should divisible by 400 for leap year
							{
							if(m==2)
							{
						if(d>29)
						{System.out.println("invalid date");
						System.exit(0);}
									}
							}
						else
						{
							if(d>28)
							{
								System.out.println("invalid date");
								System.exit(0);
							}
						}}
						else
							{if(m==2){
							if(d>29)
								{System.out.println("invalid date");
								System.exit(0);}
							}}
					}
					else
					{
						if(m==2){
							if(d>28)
							{System.out.println("invalid date");
							System.exit(0);
										}
					}}
					int newCal = (y-1)%400; // after 400 years the calender repeates 
					int ncent = (newCal)/100; // now check for the cewnturies completed
					//ncent = completed century
					// newcal for new calender started
					switch(ncent)
					{				//c for century odd days
							case 0:{
								c=0;
							break;}
							case 1:{
								c=5;
							break;}
							case 2:{
								c=3;
							break;}
							case 3:{
								c = 1;
							break;}}
					//Lets check for leap year
					int acent=newCal % 100;	
					int yrs = (acent + acent/4)%7;
					int yr = (yrs + c ) % 7;
					
					if(y%4==0)  //Month		
				{
						if(y%100==0){
							if(y%400==0)
								l=1;    // In leap year the Feb is having 1 odd day.
							else
								l=0;}  // In regular year the Feb is having 0 day.
						else
							l=1;}
					// now the odd days in the month
					// from feb we have to check for the leap year condition
					int m1=3;
					int m2=3+l;
					int m3=6+l;
					int m4=8+l;
					int m5=11+l;
					int m6=13+l;
					int m7=16+l;
					int m8=19+l;
					int m9=21+l;
					int m10=24+l;
					int m11=26+l;
					
					switch(m-1){
						case 0:{
							m=0;
							break;}
						case 1:{
							m = m1;
							break;}
						case 2:{
							m = m2;
							break;}
						case 3:{
							m = m3;
							break;}
						case 4:{
							m = m4;
							break;}
						case 5:{
							m = m5;
							break;}
						case 6:{
							m = m6;
							break;}
						case 7:{
							m = m7;
							break;}
						case 8:{
							m = m8;
							break;}
						case 9:{
							m = m9;
							break;}
						case 10:{
							m = m10;
							break;}
						case 11:{
							m = m11;
							break;}}
					
					//Now check for the odd days
					int day = (d+ m +yr)%7;  
					switch (day){
						case 0:{
								System.out.println("You born on SUNDAY");
								break;}
						case 1:{
								System.out.println("You born on MONDAY");
								break;}
						case 2:{
								System.out.println("You born on TUESDAY");
								break;}
						case 3:{
								System.out.println("You born on WEDNESAY");
								break;}
						case 4:{
								System.out.println("You born on THURSDAY");
								break;}
						case 5:{
								System.out.println("You born on FRIDAY");
								break;}
						case 6:{
								System.out.println("You born on SATURDAY");
								break;}
						default:
								System.out.println("invalid input");}
						}
}
