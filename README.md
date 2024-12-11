/**Sayı Tahmin Oyunu
Açıklama:
Bilgisayar rastgele bir sayı seçer (örneğin, 1 ile 100 arasında- Buradaki sınırların ne olacağı, sınırların kullanıcıdan alınıp alınmayacağı vb detaylar programlama kabiliyetinize veya sizin kurgunuza bağlı olarak değişiklik gösterebilir). Kullanıcı sayıyı tahmin etmeye çalışır. Her tahmin sonrası program, tahminin “daha büyük” veya “daha küçük” olduğunu söyler.
Kullanıcı doğru tahmini yapana kadar devam eder ve sonunda kaç denemede bildiğini gösterir.
**/
import java.util.Scanner;
import java.util.Random;

public class Yarisma {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Hoşgeldiniz lütfen kurallara uyunuz");

        System.out.println("Alt sınırı giriniz : ");
        int altsinir = scanner.nextInt();

        System.out.println("Üst sınırı giriniz :");
        int ustsinir = scanner.nextInt();


        Random random = new Random();
        int rastgelesayi = random.nextInt(ustsinir - altsinir + 1) + altsinir;

        System.out.println("Bilgisayar, " + altsinir + " ile " + ustsinir + " arasında bir sayı seçti.");
        System.out.println("Tahmin etmeye başlayın!");

        int tahminsayisi = 0;
        int tahmin;


        System.out.println("Lütfen tahmininizi giriniz :");


        for (int i = 0; i < Integer.SIZE; i++) {
            tahminsayisi++;


            tahmin = scanner.nextInt();

            if (tahmin < rastgelesayi) {
                System.out.println("Lütfen daha büyük bir sayı giriniz.");
            } else if (tahmin > rastgelesayi) {
                System.out.println("Lütfen daha küçük bir sayı giriniz.");
            } else {

                System.out.println("Tebrikler! Doğru sayıyı girdiniz. Sayıyı " + tahminsayisi + " denemede buldunuz.");

            }
        }

    }
}
