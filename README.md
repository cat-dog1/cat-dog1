- 👋 Hi, I’m @cat-dog1



Method ref:
1.		List<String> fruites = new ArrayList<String>();
		fruites.add("Apple");
		fruites.add("Orange");
		fruites.add("Pine-Apple");
		fruites.add("Banana");
		fruites.add("Mango");
		
		fruites.forEach(System.out::println);

2.		class Food{  
			@FunctionalInterface 
			interface IFoodService{  
	    			void display();
	    
			}  
			public Food(){  
       				System.out.println("Food Constructor");  
   			 } 
			public void Display() {
				System.out.println("New My Method");
			}
		} 


		Food food=new Food();
		IFoodService iFoodService = food::Display;  
        	iFoodService.display();

Array List:
1.		List<Integer> intSeq = Arrays.asList(10, 20, 30, 40, 50);
		intSeq.sort(Collections.reverseOrder());
		intSeq.forEach(x -> System.out.print(x + ", "));

2.		// New way:
		List<Integer> list2 = Arrays.asList(1, 2, 3, 4, 5, 6, 7);
		list2.forEach(n -> System.out.println(n));
		
		// or we can use :: double colon operator in Java 8
		list.forEach(System.out::println);
3.		//Tot
		List<Integer> listOfMarks= Arrays.asList(1, 2, 3, 4, 5, 6, 7);
		ICalculateService icalculateService = total -> listOfMarks.stream().mapToInt(Integer ::intValue).sum();	

Normal Lamda Expression:
1.		interface MathOperation {
			int operation(int a, int b);
		}
		// with type declaration
		MathOperation addition = (int a, int b) -> a + b;

		// with out type declaration
		MathOperation subtraction = (a, b) -> (a - b);

		// with return statement along with curly braces
		MathOperation multiplication = (int a, int b) -> {
			return a * b;
		};

		// without return statement and without curly braces
		MathOperation division = (int a, int b) -> a / b;

2.		interface ICalcculater{
	
			int add(int no1, int no2);
	
			default int min(int no1, int no2){
				return (no1 - no2);
			}
	
			static int mul(int no1, int no2){
				return (no1 * no2);
			}
			}
			//Constructor call
		ICalcculater iCalcculater = (x, y) -> (x + y);
		
		//objectname. for default methods
		iCalcculater.min(10, 11);
		
		//Interface. Name for Static methods
		ICalcculater.mul(2,3);

Thread:

1.		Runnable r1 = new Runnable() {
			@Override
			public void run() {
				for (int i = 0; i < 10; i++) {
					System.out.print(i + ", ");
				}
			}
		};

		new Thread(() -> IntStream.iterate(0, i -> i + 1).limit			(10).forEach(i -> {
			System.out.print(i + ", ");
			})).start()

2.		Runnable r1 = () -> {
			for (int i = 0; i < 5; i++) {
			System.out.print(i + ", ");
			}
		};
		r1.run();



//New Added
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class See {

	public static void main(String[] args) {
		

		//thread / runnable & for loop=======================================================
		//Type 1
		new Thread( () -> IntStream.iterate(1, i -> i + 1).limit(5).forEach(i -> {System.out.print(i + "");}) ).start();
		
		//Type 2
		Runnable r = () -> {
			for (int row = 1; row <= 5; row++) { 
				for (int column = 1; column <= 5; column++) 
				{ 
					System.out.print(column); 
				} 
				System.out.println(); 
			}
		};
		r.run();
		
		//Array list==========================================================================		_/
//		ITrafficService objITrafficService = total -> speedinCheckPoint.stream().mapToDouble(Double::doubleValue).sum() / speedinCheckPoint.size();
//		System.out.println("Speed -: " + objITrafficService.checkSpeed(speedinCheckPoint));
		
//		ITrafficServicee SpeedMonitor = l -> {
//			double total = 0;
//			for(double speed: l){
//				 total = total + speed;
//			}
//			double averageSpeed = total/ l.size();
//			
//			if(averageSpeed >= 100.0){ 
//				return "Issue Fine";
//			}
//			return null;			
//		};
		
		//Data adding to the Array
//		List<Integer> intSeq = Arrays.asList(10, 20, 30, 40, 50);
//		List<Integer> intSeq = new ArrayList<Integer>();
//		intSeq.add(34);
		
		//Sorting and Printing
//		intSeq.sort(Collections.reverseOrder());
//		intSeq.forEach(e -> System.out.println(e + ""));
		
		
		//normal java method====================================================================	_/
		//No Parameters
//		ICommunicable iCommunicable = () -> System.out.println("Hello Udara !!!");
//		iCommunicable.sayHello();
//		iCommunicable.display();     //use interface object for default methods
//		ICommunicable.displayName(); // use Functional interface name for static methods
		
		//One Parameter
//		ICommunicable2 iCommunicable2 = name -> System.out.println("Hello " + name + " !!!");
//		iCommunicable2.sayHello("Udara");
		
		//Multy Parameters
//		IConcaternate iConcaternate = (branch, institute) -> System.out.println(branch + institute);
//		iConcaternate.concat("Malabe ", "SLIIT");
		
		
		//Method reference 3 types==============================================================
		List<String> vehicles = new ArrayList<String>(); 
		vehicles.add("Car"); 
		vehicles.add("Bus"); 
		vehicles.add("Van"); 
		vehicles.add("Jeep"); 
		vehicles.add("Lorry"); 
		
		//Print using Lambda
		vehicles.forEach(e -> System.out.println(e));
		
		//Print using Method reference
		vehicles.forEach(System.out::println);
		

	}

}
