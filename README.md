using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using System;


namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {

            IWebDriver driver = new ChromeDriver();
            //Google Chrome açılışını yapar.
            //Aynı zamanda driver diye nesne tanımlamış olduk.
            //Bu nesne üzerinden işlemleri yapacağız.
            driver.Navigate().GoToUrl("http://www.n11.com");
            //Bu driver nesnesi ile gitmek istediğimiz sayfayı göstereceğiz.

            
            // KULLANICI GİRİŞİNİ TEST ETME
            driver.FindElement(By.LinkText("Giriş Yap")).Click();
            //Ana sayfadaki Giriş Yap linktxtini arayıp mause kliğini gerçekleştirir.
            driver.FindElement(By.Name("email")).SendKeys("ad.soyad@gmail.com");
            //Email kısmına kullanıcının mail adresini yazar.
            driver.FindElement(By.Name("password")).SendKeys("abcabcabc");
            //şifre kısmına kullanıcının siteye giriş şifresini yazar
            driver.FindElement(By.Id("loginButton")).Click();
            //Üye girişi butonunu tıklayarak kullanıcı siteye olmuş ise siteye girişi sağlanır.
            
            

            driver.FindElement(By.Id("searchData")).SendKeys("Samsung");
            //Samsnug ürününü arama çubuğuna yazma

            driver.FindElement(By.ClassName("searchBtn")).Click();
            //Ürünü aratma

            Console.WriteLine("Samsung için sonuçlar arandı");

            driver.FindElement(By.ClassName("currentPage")).Clear();
            driver.FindElement(By.ClassName("currentPage")).SendKeys("2" + Keys.Return);
            //Aratılan ürün sonucunun 2.sayfasına geçme

            //driver.FindElement(By.ClassName("","position")).SendKeys("31");
            string sRowValue = driver.FindElement(By.XPath(".//*[@id='post-2924']/div/table/tbody/tr[31]")).Text;
            Console.WriteLine("Yazdığım yazı ekrana geldi.");
            //İşlem gerçekleşirse oluşacak çıktıyı buraya yazıyoruz.

            //driver.Quit();
            //Açtığımız Google Chrome’u kapattık ve test işlemini sona erdirdik.


            //Or can be written as


        }
    }
}
