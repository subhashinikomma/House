import java.util.*;
class HouseConstructionCostEstimation
{
	void costPerSquareFeet()
	{
		Scanner sc = new Scanner(System.in);
		String standard;
		int totalCost = 0,costPerSquareFeet = 0,totalArea = 0;
		String automation = "";
		boolean checkAutomation = true;
		System.out.printf("Enter the standard(Normal Standard/Above Standard/High Standard)(Case sensitive) : ");
		standard = sc.nextLine();
		if(standard.equals("High Standard")) 
		{
			System.out.printf("Do you need full automation in house ?(Yes/No) ");
			automation = sc.nextLine();
		}
		if(automation.equals("Yes") || automation.equals("yes") || automation.equals("YES"))
			checkAutomation = true;
		else if(automation.equals("No") || automation.equals("no") || automation.equals("NO"))
			checkAutomation = false;
		System.out.printf("Enter the total area(in square feets):");
		totalArea = sc.nextInt();
		if(standard.equals("Normal Standard"))
			costPerSquareFeet = 1200;
		else if(standard.equals("Above Standard"))
			costPerSquareFeet = 1500;
		else if(standard.equals("High Standard") && checkAutomation == true)
			costPerSquareFeet = 2500;
		else if(standard.equals("High Standard") && checkAutomation == false)
			costPerSquareFeet = 1800;
		totalCost = costPerSquareFeet * totalArea;
		System.out.printf("Estimated house construction cost : %dINR\n",totalCost);
	}
}
