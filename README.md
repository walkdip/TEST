# TEST
package selenium;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.Keys;
import org.openqa.selenium.interactions.Actions;
import org.testng.annotations.Parameters;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
import org.testng.annotations.AfterTest;
public class CrossBrowsertestingTesting
{
WebDriver driver;
@Parameters("browser")
@BeforeTest
public void start(String browser)
{
 if(browser.equalsIgnoreCase("chrome"))
 {
  System.setProperty("webdriver.chrome.driver","C:\\Users\\vanga\\Downloads\\Selenium\\Selenium jars\\chromedriver.exe");
  driver= new ChromeDriver();
  driver.get("https://www.google.com/");
  driver.manage().window().maximize();
 }
  else if(browser.equalsIgnoreCase("firefox"))
  {
    System.setProperty("webdriver.gecko.driver","C:\\Users\\vanga\\Downloads\\Selenium\\Selenium jars\\chromedriver.exe");
    driver= new ChromeDriver();
	driver.get("https://www.google.com/");
	driver.manage().window().maximize();
	  
  }
		
	}
    @Test
    public void test()throws Exception
    {
     driver.findElement(By.name("q")).sendKeys("selenium");
     Actions a=new Actions(driver);
     a.sendKeys(Keys.ENTER);
     a.build().perform();
     Thread.sleep(1000);
     a.sendKeys(Keys.END);
     a.build().perform();	
    }
    @AfterTest
    public void end()throws Exception
    {
       Thread.sleep(1000);
       driver.close();
     }
    

}
