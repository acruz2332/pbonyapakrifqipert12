**Mahasiswa**
```java
package Paket;

/**
 *
 * @author akbar
 */
public class Mahasiswa extends Manusia {
    private String nama;
    public Mahasiswa(String nama){
        super(nama);
    }
    @Override
    public void setNama(String nama){
        super.setNama(nama+nama);
    }
    
    @Override
    public String toString(){
        return "nama = "+ super.getNama();
    }
}
```

**Main**
```java
package Paket;

/**
 *
 * @author akbar
 */
public class Main {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Manusia a1 = new Manusia("Agus");
        System.out.println(a1);
        a1.setNama("Aji");
        System.out.println(a1.getNama());
        
        Manusia a2 = new Mahasiswa("Budi");
        System.out.println(a2);
        a2.setNama("Bayu");
        System.out.println(a2.getNama());
        
        Manusia b1 = new Mahasiswa("Susi");
        System.out.println(b1);
        b1.setNama("Santi");
        System.out.println(b1.getNama());
    }
    
}
```

**Manusia**
```java
package Paket;

/**
 *
 * @author akbar
 */
public class Manusia {
    private String nama;
    public Manusia(String nama){
        this.nama = nama;
    }
    public String getNama(){
        return nama;
    }
    public void setNama(String nama){
        this.nama = nama;
    }
    @Override
    public String toString(){
        return "Nama = "+ nama;
    }
}
```
