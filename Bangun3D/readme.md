**Balok**
```java
package Bangun3D;
import Bangun2D.PerseegiPanjang;
/**
 *
 * @author akbar
 */
public class Balok extends PerseegiPanjang {
    private double tinggi;
    
    public Balok(double panjang, double lebar, double tinggi){
        super(panjang, lebar);
        this.tinggi = tinggi;
    }
    
    public double getTinggi(){
        return tinggi;
    }
    
    public void setTinggi(double tinggi){
        this.tinggi = tinggi;
    }
    
    @Override
    public double getLuas(){
        return 2* (getPanjang()*getLebar()+getPanjang()*tinggi+getLebar()*tinggi);
    }
    
    @Override
    public double getKeliling(){
        return 4* (getPanjang()+getLebar()+tinggi);
    }
    
    public double getLuasAlas(){
        return super.getLuas();
    }
    
    public double getVolume(){
        return super.getLuas()*tinggi;
    }
    
    @Override
    public String toString(){
        return "panjang="+getPanjang()+", lebar="+getLebar()+
                "tinggi="+tinggi;
    }
}
```

**Kerucut**
```java
package Bangun3D;
import Master.Matematika;
/**
 *
 * @author akbar
 */
public class Kerucut extends Tabung {
    //private double phi = 22.0/7;
    public Kerucut(double r, double tinggi){
        super(r,tinggi);
    }
    @Override
    public double getLuas(){
        return getLuasAlas()+Matematika.phi*getR()*getSisiMiring();
    }
    public double getSisiMiring(){
        return Matematika.getMiring(getR(), getTinggi());
    }
    @Override
    public double getVolume(){
        return super.getVolume()/3;
    }
    
    @Override
    public String toString(){
        return "r="+getR()+"tinggi="+getTinggi();
    }
}
```

**Kubus**
```java
package Bangun3D;
import Bangun2D.Persegi;
/**
 *
 * @author akbar
 */
public class Kubus extends Persegi {
    public Kubus(double sisi){
        super(sisi);
    }
    
    @Override
    public double getLuas(){
        return 6*super.getLuas();
    }
    @Override
    public double getKeliling(){
        return 12*getSisi();
    }
    public double getLuasAlas(){
        return super.getLuas();
    }
    public double getVolume(){
        return super.getLuas()*getSisi();
    }
    
    @Override
    public String toString(){
        return "sisinya="+getSisi();
    }
}
```

**Main2**
```java
package Bangun3D;

import Bangun2D.Persegi;

/**
 *
 * @author akbar
 */
public class Main2 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Persegi P1 = new Kubus(4);
        System.out.println(P1.getLuas());
    }
    
}
```

**Tabung**
```java
package Bangun3D;

/**
 *
 * @author akbar
 */
public class Tabung {
    private double phi = 22.0/7;
    private double r;
    private double tinggi;
    
    public Tabung(double r, double tinggi){
        this.r = r;
        this.tinggi = tinggi;
    }
    public double getR(){
        return r;
    }
    public void setR(double r){
        this.r = r;
    }
    public double getTinggi(){
        return tinggi;
    }
    public void setTinggi(double tinggi){
        this.tinggi = tinggi;
    }
    public double getLuas(){
        return 2*getLuasAlas()+ 2*phi*r*tinggi;
    }
    public double getLuasAlas(){
        return phi*r*r;
    }
    public double getVolume(){
        return phi*r*r*tinggi;
    }
    @Override
    public String toString(){
        return "r="+r+"tinggi="+tinggi;
    }
}```
