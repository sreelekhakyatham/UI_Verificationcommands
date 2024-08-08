//# UI_Verificationcommands

package UI_Verificationcommands;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class runTime_Object {

	public static void main(String[] args) throws Exception
	{
		WebDriver driver=new ChromeDriver();
		driver.get("https://www.facebook.com/reg/");
		driver.manage().window().maximize();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(300));
		
		WebElement Email=driver.findElement(By.xpath("//input[contains(@name,'reg_email__')]"));
		Email.clear();
		Email.sendKeys("info@mindqsystems.com");
		Thread.sleep(3000);
		
		WebElement Retype_Email=driver.findElement(By.xpath("(//input[@type='text'])[4]"));
		if (Retype_Email.isDisplayed()) 
		{
			Retype_Email.sendKeys("info@mindqsystems.com");
		} 
		else 
		{
			System.out.println("Retype_Email is not displayed");
		}
		
		
		
	}

}
