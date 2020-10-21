package com.herokuapp.theinternet;
import java.util.*;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Point;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import java.util.concurrent.TimeUnit;
/**
 * Logs you into firebase and downloads all the .txt and .log files for a given crashlytics issue.
 */
public class TestFirebase {
	
	
	public static void main(String[] args) throws InterruptedException {
		
		System.setProperty("webdriver.chrome.driver", "D:\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		// Maximize window
		driver.manage().window().maximize();
		// open test page
		String url = "https://console.firebase.google.com/";
		driver.get(url);
		System.out.println("page is open");
	
		driver.findElement(By.id("identifierId")).sendKeys("9angel_jose@singaporeair.com.sg"); 

        driver.manage().timeouts().implicitlyWait(20, TimeUnit.SECONDS);      

       // WebDriverWait wait=new WebDriverWait(driver, 20);               

        driver.findElement(By.xpath("//div[@class='VfPpkd-RLmnJb']")).click();   
        

        driver.manage().timeouts().implicitlyWait(50, TimeUnit.SECONDS);        

        driver.findElement(By.xpath("(//input[contains(@class,'whsOnd zHQkBf')])[1]")).sendKeys("Sepsep@23");             

        driver.findElement(By.xpath("(//div[@class='VfPpkd-RLmnJb'])[1]")).click(); 
        
       driver.findElement(By.xpath("//div[contains(@class,'project-display-name ng-star-inserted')])[1]")) .click();
   driver.findElement(By.xpath("(//a[contains(@mattooltipposition,'right')])[2]")).click();
   driver.findElement(By.xpath("(//div[contains(@class,'mat-select-arrow-wrapper')])[2]")).click();
   driver.findElement(By.xpath("((//span[@class='resource-selector-text'][contains(.,'SingaporeAir - Amadeus(PRD)')])[2]")).click();
   driver.findElement(By.xpath("(//span[contains(.,'Filter')])[1]")).click();
   driver.findElement(By.xpath("(//div[contains(@class,'value-wrapper ng-star-inserted')])[1]")).click();
   driver.findElement(By.xpath("(//span[contains(@class,'mat-button-wrapper')])[13]")).click();
   
   List <WebElement> namesElements = driver.findElements(By.xpath("//mat-card[contains(@class,'c9s-issues-table-container mat-card mat-focus-indicator')]"));
   List<String> names = new ArrayList<String>();
   for(WebElement namesElement : namesElements) {
	   names.add(namesElement.getText());
   }
   
   WebElement nextButtonClassName =driver.findElement(By.xpath("//*[@class='mat-paginator-icon']"));
   
   while(!((List<WebElement>) nextButtonClassName).contains("disabled"))
 
   {
	   driver.findElement(By.xpath("//*[@class='mat-paginator-icon']")).click();
	   namesElements =driver.findElements(By.xpath("//mat-card[contains(@class,'c9s-issues-table-container mat-card mat-focus-indicator')]"));	   
	   for(WebElement namesElement : namesElements) {
		   names.add(namesElement.getText());
	   }
		   
		   driver.findElement(By.xpath("//*[@class='mat-paginator-icon']")).click();
   }
   for(String name:names)
   {System.out.println(name);
   }
   int totalNames=names.size();
   System.out.println("total:"+totalNames);
	}
	
 //svg[contains(@class,'mat-paginator-icon')]
//span[@class='mat-button-wrapper'][contains(.,'Apply')]

   //span[contains(.,'Filter')])[1]
		//Login
		 //driver.findElement(By.xpath("//div[@class='w1I7fb'])[1]")).click();
	}

