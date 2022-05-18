**Mahasiswa**
```java
package latihanstatic;

/**
 *
 * @author akbar
 */
public class Mahasiswa {
    private static String prodi;
    private String nama;

    public Mahasiswa(String nama){
        this.nama = nama;
    }
    public static String getProdi(){
        return prodi;
    }
    public static void setProdi(String prodi){
        Mahasiswa.prodi = prodi;
    }
    public String getNama(){
        return nama;
    }
    public void setNama(String nama){
        this.nama = nama;
    }
    @Override
    public String toString(){
        return "nama="+nama+" prodi="+prodi;
    }
}
```

**Main3**
```java
package latihanstatic;

/**
 *
 * @author akbar
 */
public class Main3 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        System.out.println(Mahasiswa.prodi);
        //System.out.println(Mahasiswa.nama);
        
        Mahasiswa st1 = new Mahasiswa();
        System.out.println(st1.prodi);
        System.out.println(st1.nama);
        
        Mahasiswa st2 = new Mahasiswa();
        System.out.println(st2.prodi);
        System.out.println(st2.nama);
        
        st1.prodi = "Teknologi RPL";
        st1.nama = "Agus";
        st2.prodi = "TRPL";
        st2.nama = "Budi";
        
        System.out.println(st1.prodi);
        System.out.println(st1.nama);
        
        System.out.println(st2.prodi);
        System.out.println(st2.nama);
        
        Mahasiswa.prodi = "Software Engineering Technology";
        System.out.println(st1.prodi);
        System.out.println(st1.nama);
        
        System.out.println(st2.prodi);
        System.out.println(st2.nama);
        
        Mahasiswa.setProdi("Software Engineering Technology");
        System.out.println(st1.getProdi());
        System.out.println(st1.getNama());
        
        System.out.println(st2.getProdi());
        System.out.println(st2.getNama());
    }
    
}
```
