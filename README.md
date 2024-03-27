package modul2_202357201055;
import java.util.Scanner;
public class Modul2_202357201055 {
    public static void main(String[] args) {
        int bil = 10;
        String b[] = {"a", "b", "c"};
        try {
            System.out.println(bil / 0);
            System.out.println(b[3]);
        } catch (ArithmeticException ai) {
            System.out.println("Error Aritmetik");
            System.out.println(ai.getMessage());
        } catch (ArrayIndexOutOfBoundsException n) {
            System.out.println("Error karena melebihi kapasitas array");
            System.out.println(n.getMessage());
        } catch (Exception e) {
            System.out.println("Ada error");
            System.out.println(e.getMessage());
        }
        methodx mt = new methodx();
        mt.calculateVolume();
    }
}
class methodx {
    public double luas_lingkaran(int diameter){
        int jari2 = diameter / 2;
        double luas = Math.PI * Math.pow(jari2, 2);
        return luas;
    }
    public void calculateVolume() {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Pilih bangun geometri (1. Tabung, 2. Kerucut, 3. Bola): ");
        int choice = scanner.nextInt();
        switch (choice) {
            case 1:
                System.out.println("Masukkan diameter tabung: ");
                double diameterTabung = scanner.nextDouble();
                System.out.println("Masukkan tinggi tabung: ");
                double tinggiTabung = scanner.nextDouble();
                double volumeTabung = luas_lingkaran((int)diameterTabung) * tinggiTabung;
                System.out.println("Volume tabung: " + volumeTabung);
                break;
            case 2:
                System.out.println("Masukkan diameter kerucut: ");
                double diameterKerucut = scanner.nextDouble();
                System.out.println("Masukkan tinggi kerucut: ");
                double tinggiKerucut = scanner.nextDouble();
                double volumeKerucut = (1.0/3) * luas_lingkaran((int)diameterKerucut) * tinggiKerucut;
                System.out.println("Volume kerucut: " + volumeKerucut);
                break;
            case 3:
                System.out.println("Masukkan diameter bola: ");
                double diameterBola = scanner.nextDouble();
                double volumeBola = (4.0/3) * Math.PI * Math.pow(diameterBola / 2, 3);
                System.out.println("Volume bola: " + volumeBola);
                break;
            default:
                System.out.println("Pilihan tidak valid.");
        }
        
    }
}
