# Amazon-Search-Order-Product
Automation testing for product search on Amazon and Ordering
package com.apex.amazon.core;

import org.openqa.selenium.By;
import org.openqa.selenium.By.ByXPath;
import org.testng.annotations.Test;

public class AmazonLogInTest_ng extends ApexBaseCoreAmazon {

	@Test
	public void amazonSignInBuyiPhone7() throws InterruptedException {
		driver.findElement(ByXPath.xpath("html/body/div[1]/header/div/div[2]/div[2]/div/a[1]/span[1]")).click();

		driver.findElement(By.id("ap_email")).sendKeys(EMAIL);
		driver.findElement(By.id("ap_password")).sendKeys(PASSWORD);
		driver.findElement(By.id("signInSubmit")).click();

		driver.findElement(By.id(SEARCHBOX)).sendKeys("iphone7 Case,Supcase");
		driver.findElement(ByXPath.xpath("html/body/div[1]/header/div/div[1]/div[5]/div/div/div/div[1]")).click();
		driver.findElement(ByXPath
				.xpath("html/body/div[1]/div[2]/div[3]/div[2]/div/div[4]/div[1]/div/ul/li[1]/div/div/div/div[2]/div[2]/a/h2"))
				.click();
		driver.findElement(
				ByXPath.xpath("html/body/div[3]/div[10]/div[4]/div[2]/div/form/div/div/div[1]/div[3]/span/span/input"))
				.click();
		Thread.sleep(1000);
		driver.findElement(
				ByXPath.xpath("html/body/div[2]/div/div[2]/div[7]/div[1]/div/div[2]/div/div/div/span[2]/span/a"))
				.click();
		Thread.sleep(1000);
		driver.findElement(By.id("enterAddressFullName")).sendKeys(FULLNAME);
		driver.findElement(By.id("enterAddressAddressLine1")).sendKeys(STREETNO);
		driver.findElement(By.id("enterAddressAddressLine2")).sendKeys(HOMENO);
		driver.findElement(By.id("enterAddressCity")).sendKeys(CITY);
		driver.findElement(By.id("enterAddressStateOrRegion")).sendKeys(STATE);
		driver.findElement(By.id("enterAddressPostalCode")).sendKeys(ZIP);
		driver.findElement(
				ByXPath.xpath("html/body/div[5]/div[2]/div[2]/div[1]/div/div[1]/div/form/div[1]/div[7]/div/select"))
				.click();

		driver.findElement(ByXPath
				.xpath("html/body/div[5]/div[2]/div[2]/div[1]/div/div[1]/div/form/div[1]/div[7]/div/select/option[233]"))
				.click();
		driver.findElement(By.id("enterAddressPhoneNumber")).sendKeys(PHONE);
		driver.findElement(
				ByXPath.xpath("html/body/div[5]/div[2]/div[2]/div[1]/div/div[1]/div/form/div[8]/span/span/input"))
				.click();

		Thread.sleep(4000);
		
		}
 

}






package com.apex.amazon.core;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;

public class ApexBaseCoreAmazon implements IApexBaseCoreAmazon{
	public WebDriver driver = null;
 

  @BeforeMethod
  public void beforeMethod() {
	// driven creating and setting up, timeout
			// open the browser
			driver = new FirefoxDriver();
			driver.get(URL);

  }

  @AfterMethod
  public void afterMethod() {
	  driver.close();
  }

}




package com.apex.amazon.core;

public interface IApexBaseCoreAmazon {
	public static final String URL = "https://www.amazon.com";
	public static final String EMAIL = "preity1994@yahoo.com";
	public static final String PASSWORD = "ABCDE123";
    public static final String SEARCHBOX = "twotabsearchtextbox";
    public static final String FULLNAME = "Tania Preity";
	public static final String STREETNO = "1234 BayPoint";
	public static final String HOMENO = "1234";
	public static final String CITY = "San Fransisco";
	public static final String STATE = "California";
	public static final String ZIP = "94538";
	public static final String PHONE = "123456789";

}
