# Xpath
package day04_xpath;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import java.time.Duration;
public class C02_Xpath {
    public static void main(String[] args) throws InterruptedException {

        System.setProperty("webdriver.chrome.driver","src/resources/drivers/chromedriver.exe");
        WebDriver driver= new ChromeDriver();
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(15));
        
   
        driver.get("https://the-internet.herokuapp.com/add_remove_elements/");
        driver.findElement(By.xpath("//*[text()='Add Element']")).click();
       
        WebElement deleteButonu= driver.findElement(By.xpath("//button[@class='added-manually']"));
        if (deleteButonu.isDisplayed()){
            System.out.println("delete butonu testi PASSED");
        } else {
            System.out.println("delete butonu testi FAILED");
        }
       
        Thread.sleep(3000);
        deleteButonu.click();
        
        WebElement addRemoveYaziElementi= driver.findElement(By.xpath("//h3"));
        if (addRemoveYaziElementi.isDisplayed()){
            System.out.println("addRemoveYazi testi PASSED");
        } else {
            System.out.println("addRemoveYazi testi FAILED");
        }
        Thread.sleep(3000);
        driver.close();
    }
}

