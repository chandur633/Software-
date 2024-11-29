Prg 1


package abcd;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
public class pr1 {
	 public static void main(String[] args) {
	        // Setup WebDriver (make sure the chromedriver executable is in your path)
	        WebDriver driver = new ChromeDriver();
	        // Navigate to the LMS login page
driver.get("http://lms.nmit.ac.in/moodle/login/index.php/");
	        // Fetch and print the title before login
	        String loginPageTitle = driver.getTitle();
	        System.out.println("Login Page Title: " + loginPageTitle);
	        // Interact with the login form
	        driver.findElement(By.name("username")).sendKeys("27619");
driver.findElement(By.name("password")).sendKeys("your_passowrd");
driver.findElement(By.id("loginbtn")).submit();
	        // Wait for 10 seconds for the page to load (replace with explicit wait in real use cases)
	        try {
	            Thread.sleep(10000);
	        } catch (InterruptedException e) {
	            e.printStackTrace();
	        }
	        // Fetch and print the title after login6
	        String postLoginTitle = driver.getTitle();
	        System.out.println("Post-Login Page Title: " + postLoginTitle);
	        // Validate the title after login (update the title string with the actual value you see)
	        if (postLoginTitle.equals("Dashboard")) {  // Replace "Dashboard" with the correct title after login
	            System.out.println("Test Passed");
	        } else {
	            System.out.println("Test Failed");
	            System.out.println("Actual Title: " + postLoginTitle);
	        }
	        // Close the browser
//	        driver.close();
	    }
}






Prg 2

package abcd;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;

public class pr2 {
	 public static void main(String[] args) {
	        // Setup WebDriver (make sure the chromedriver executable is in your path)
	        WebDriver driver = new ChromeDriver();
	        // Navigate to the LMS login page
	        driver.get("http://lms.nmit.ac.in/moodle/login/index.php/");
	        // Fetch and print the title before login
	        String loginPageTitle = driver.getTitle();
	        System.out.println("Login Page Title: " + loginPageTitle);
	        // Interact with the login form
	        driver.findElement(By.name("username")).sendKeys("27145");
	        driver.findElement(By.name("password")).sendKeys("wrong_password");
	        driver.findElement(By.id("loginbtn")).submit();
	        // Wait for 10 seconds for the page to load (replace with explicit wait in real use cases)
	        try {
	            Thread.sleep(10000);
	        } catch (InterruptedException e) {
	            e.printStackTrace();
	        }
	        // Fetch and print the title after login
	        String postLoginTitle = driver.getTitle();
	        System.out.println("Post-Login Page Title: " + postLoginTitle);
	        // Validate the title after login (update the title string with the actual value you see)
	        if (postLoginTitle.equals("Dashboard")) {  // Replace "Dashboard" with the correct title after login
	            System.out.println("Test Passed");
	        } else {
	            System.out.println("Test Failed");
	            System.out.println("Actual Title: " + postLoginTitle);
	        }
	 }
}



Prg 3

package abcd;

import java.time.Duration;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class prgm3 {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        // Open Google and search for "NMIT"
        driver.get("https://www.google.com/");
        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
        WebElement searchBox = driver.findElement(By.name("q"));
        searchBox.sendKeys("NMIT");
        searchBox.sendKeys(Keys.ENTER);
        // Wait for the first result and click on it
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
        WebElement firstResult = wait.until(ExpectedConditions.elementToBeClickable(By.cssSelector("h3"))); 
        System.out.println("Clicking on first result: " + firstResult.getText());
        firstResult.click();
        // Wait for the NMIT website to load
        wait.until(ExpectedConditions.urlContains("nmit"));
        System.out.println("Successfully navigated to the page: " + driver.getCurrentUrl());
        // Close the browser and handle any errors
        try {
            driver.quit();
            System.out.println("Test completed and browser closed.");
        } catch (Exception e) {
            System.out.println("An error occurred while closing the browser: " + e.getMessage());
            e.printStackTrace();
        }
    }
}


Prg 4

package abcd;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
import java.time.Duration;


public class prgm4 {
	public static void main(String[] args) {
		 WebDriver driver = new ChromeDriver();
	        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));        
	            // Navigate to the form
	            driver.get("https://www.jotform.com/build/242983020566458?s=templates2");
	            driver.findElement(By.id("first_4")).sendKeys("Divya");	 
	            driver.findElement(By.id("last_4")).sendKeys("K");
	            driver.findElement(By.id("label_input_10_0")).click();
	            driver.findElement(By.id("label_input_10_1")).click();
	            driver.findElement(By.id("label_input_10_2")).click();
	            driver.findElement(By.id("label_input_10_3")).click();
	            driver.findElement(By.id("label_input_11_0")).click();
	            driver.findElement(By.id("label_input_11_1")).click();
	            driver.findElement(By.id("label_input_11_2")).click();
	            driver.findElement(By.id("label_input_11_3")).click();
	            WebElement genderSelect = driver.findElement(By.id("input_3"));
	            Select gender = new Select(genderSelect);
	            gender.selectByValue("Female"); 
	            driver.findElement(By.id("input_5")).sendKeys("061");
	            driver.findElement(By.id("input_6")).sendKeys("divya@gmail.com");
	            WebElement courseSelect = driver.findElement(By.id("input_7"));
	            Select course = new Select(courseSelect);
	            course.selectByValue("Math 101");
	}

}



Prg 7

package abcd;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import java.time.Duration;

public class prgm8 {
	public static void main(String[] args) {
		WebDriver driver = new ChromeDriver();
		try {
			driver.get("https://the-internet.herokuapp.com/upload");
			driver.manage().window().maximize();
			driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
    		WebElement fileInput = driver.findElement(By.id("file-upload"));
    		fileInput.sendKeys("C:/Users/Divya K/Documents/DBMS LAB 12-06-24.txt");  		
    		WebElement uploadButton= driver.findElement(By.id("file-submit"));
    		uploadButton.click();  		
    		WebElement successMessage =driver.findElement(By.id("upload-files"));
    		if(successMessage.getText().equals("abc.txt")){
    			System.out.println("File upload successful and verified");
    		}else {
    			System.out.println("File upload verification failed.");
    		}
    	}finally {
    		driver.quit();			
		}
   }

}


Prg 9

package abcd;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import java.time.Duration;


public class prgm9 {
public static void main(String[] args) {      
        WebDriver driver = new ChromeDriver();
        try {
            driver.get("https://the-internet.herokuapp.com/javascript_alerts");
                      driver.manage().window().maximize();
            driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));           
            WebElement alertButton = driver.findElement(By.xpath("//button[text()='Click for JS Alert']"));
            alertButton.click();
            driver.switchTo().alert().accept();          
            WebElement resultText = driver.findElement(By.id("result"));
            if (resultText.getText().equals("You successfully clicked an alert")) {
                System.out.println("Simple Alert handled successfully");
            } else {
                System.out.println("Simple alert handling failed");
            }          
            Thread.sleep(2000);           
            WebElement confirmButton = driver.findElement(By.xpath("//button[text()='Click for JS Confirm']"));
            confirmButton.click();
            driver.switchTo().alert().dismiss();           
            resultText = driver.findElement(By.id("result"));
            if (resultText.getText().equals("You clicked: Cancel")) {
                System.out.println("Confirmation alert handled successfully");
            } else {
                System.out.println("Confirmation alert handling failed.");
            }           
            Thread.sleep(2000);          
            WebElement promptButton = driver.findElement(By.xpath("//button[text()='Click for JS Prompt']"));
            promptButton.click();
            driver.switchTo().alert().sendKeys("Hello, Selenium");
            driver.switchTo().alert().accept();            
            resultText = driver.findElement(By.id("result"));
            if (resultText.getText().equals("You entered: Hello, Selenium")) {
                System.out.println("Prompt alert handled successfully");
            } else {
                System.out.println("Prompt alert handling failed.");
            }
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            driver.quit();
        }	
	}
}

