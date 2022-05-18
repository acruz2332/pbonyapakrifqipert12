Source code 

**Lingkaran**
```java
package Bangun2D;
import Master.Matematika;
/**
 *
 * @author akbar
 */
public class Lingkaran {
    //private double phi = 22.0/7;
    private double r;
    
    public Lingkaran(double r){
        this.r = r;
    }
    
    public double getR(){
        return r;
    }
    
    public void setR(double r){
        this.r = r;
    }
    
    public double getLuas(){
        return Matematika.phi*r*r;
    }
    
    public double getKeliling(){
        return 2*Matematika.phi*r;
    }
    
    @Override
    public String toString(){
        return "jari = "+r;
    }
}
```

**PersegiPanjang**
```java
package Bangun2D;

/**
 *
 * @author akbar
 */
public class PerseegiPanjang {
    private double panjang;
    private double lebar;
    
    public PerseegiPanjang (double panjang, double lebar){
        this.lebar = lebar;
        this.panjang = panjang;
    }
    
    public double getPanjang(){
        return panjang;
    }
    
    public void setPanjang(double panjang){
        this.panjang = panjang;
    }
    
    public double getLebar(){
        return lebar;
    }
    
    public void setLebar(double lebar){
        this.lebar = lebar;
    }
    
    public double getLuas(){
        return panjang*lebar;
    }
    
    public double getKeliling(){
        return 2*(panjang+lebar);
    }
    
    @Override
    public String toString(){
        return "panjang = "+panjang+" lebar = "+ lebar;
    }
}
```

**Persegi**
```java
package Bangun2D;

/**
 *
 * @author akbar
 */
public class Persegi {
    private double sisi;
    
    public Persegi (double sisi){
        this.sisi = sisi;
    }
    
    public double getSisi(){
        return sisi;
    }
    
    public void setSisi(double sisi){
        this.sisi = sisi;
    }
    
    public double getLuas(){
        return sisi*sisi;
    }
    
    public double getKeliling(){
        return 4*sisi;
    }
    
    @Override
    public String toString(){
        return "Sisi = "+sisi;
    }
}
```

**Segitiga**
```java
package Bangun2D;

/**
 *
 * @author akbar
 */
public abstract class Segitiga {
    private double alas;
    private double tinggi;
    
    public Segitiga(double alas, double tinggi){
        this.alas = alas;
        this.tinggi = tinggi;
    }
    
    public double getAlas(){
        return alas;
    }
    
    public void setAlas(double alas){
        this.alas = alas;
    }
    
    public double getTinggi(){
        return tinggi;
    }
    
    public void setTinggi(double tinggi){
        this.tinggi = tinggi;
    }
    
    public double getLuas(){
        return alas*tinggi/2;
    }
    
    public abstract double getKeliling();
    
    public abstract double getSisiMiring();
    
    @Override
    public String toString(){
        return "alas = "+alas+" tinggi= "+tinggi;
    }
}
```

**SegitigaSamaKaki**
```java
package Bangun2D;
import Master.Matematika;
/**
 *
 * @author akbar
 */
public class SegitigaSamaKaki extends Segitiga {
    
    public SegitigaSamaKaki (double a, double t){
        super(a,t);
    }
    
    @Override
    public double getKeliling(){
        return getAlas()+2*getSisiMiring();
    }
    @Override
    public double getSisiMiring(){
        return Matematika.getMiring(getAlas()/2, getTinggi());
    }
    @Override
    public String toString(){
        return "a= "+ getAlas()+" t= "+ getTinggi();
    }
}
```

**SegitigaSamaSisi**
```java
package Bangun2D;
import Master.Matematika;
/**
 *
 * @author akbar
 */
public class SegitigaSamaSisi extends Segitiga {
    public SegitigaSamaSisi(double sisi){
        super(sisi,0);
        super.setTinggi(getTinggi());
    }
    
    @Override
    public double getTinggi(){
        return Matematika.getLurus(getAlas(), getAlas()/2);
    }
    
    @Override
    public void setTinggi (double tinggi){
        double alasBaru = Math.sqrt((4.0/3)*tinggi*tinggi);
        setAlas(alasBaru);
    }
    
    @Override
    public double getKeliling(){
        return 3*getAlas();
    }
    
    @Override
    public double getSisiMiring(){
     return getAlas();
    }
    
    @Override
    public String toString(){
        return "sisi="+ getAlas();
    }
}
```

**SegitigaSiku**
```java
package Bangun2D;
import Master.Matematika;
/**
 *
 * @author akbar
 */
public class SegitigaSiku extends Segitiga {
    public SegitigaSiku(double a, double t){
        super(a,t);
    }
    
    @Override
    public double getKeliling(){
        return getAlas()+ getTinggi()+ getSisiMiring();
    }
    @Override
    public double getSisiMiring(){
        return Matematika.getMiring(getAlas()/2, getTinggi());
    }
    @Override
    public String toString(){
        return "a= "+ getAlas() +", t="+ getTinggi();
    }
}
```
