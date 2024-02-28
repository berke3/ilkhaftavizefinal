# ilkhaftavizefinal

import java.util.Iterator;
import java.util.Scanner;

import javax.swing.plaf.FontUIResource;

public class Ders1_ornke_toplu {

	public static void main(String[] args) {
		try (// TODO Auto-generated method stub
				Scanner giris = new Scanner(System.in)) {
			System.out.println("Kişi Sayısını Giriniz : ");
			byte ks = giris.nextByte();
			String ad[] = new String[ks];
			byte vn[] = new byte[ks];
			byte fn[] = new byte[ks];
			byte bn[] = new byte[ks];
			byte menu;
			for (int i = 0; i < ks; i++) {
				System.out.println((i + 1) + " . ismi giriniz : ");
				ad[i] = giris.next();
				System.out.println((i + 1) + " . Vize Notu giriniz : ");
				vn[i] = giris.nextByte();
				System.out.println((i + 1) + " . Final Notu giriniz : ");
				fn[i] = giris.nextByte();
				bn[i] = (byte) (vn[i] * .4 + fn[i] * 0.6);
			} // veri alma sonu
			for (;;) {

				System.out.println("1-Listeleme\n2-İsim arama\n3-enb\n4-Enk\n5-Ortalamalar\n6-Çıkış");
				menu = giris.nextByte();
				switch (menu) {
				case 1:
					for (int i = 0; i < ks; i++) {
						System.out.println("Adı :" + ad[i]);
						System.out.println("Vize Notu : " + vn[i]);
						System.out.println("Final Notu : " + fn[i]);
						System.out.println("Başarı Notu : " + bn[i]);
					}

					break;
				case 2:
					System.out.println("Aranacak adı giriniz : ");
					String arananAd = giris.next();

					for (int i = 0; i < ks; i++) {
						if (arananAd.equalsIgnoreCase(ad[i])) {
							System.out.println("Adı :" + ad[i]);
							System.out.println("Vize Notu : " + vn[i]);
							System.out.println("Final Notu : " + fn[i]);
							System.out.println("Başarı Notu : " + bn[i]);
						}
					}

					break;
				case 3:
					byte enb = bn[0];
					for (int i = 1; i < ks; i++) {
						if (bn[i] > enb)
							enb = bn[i];
					}
					System.out.println("En büyük başarı notu : " + enb);
					for (int i = 0; i < ks; i++) {
						if (bn[i] == enb) {
							System.out.println("Adı :" + ad[i]);
							System.out.println("Vize Notu : " + vn[i]);
							System.out.println("Final Notu : " + fn[i]);
							System.out.println("Başarı Notu : " + bn[i]);
						}
					}

					break;
				case 4:
					byte enk = bn[0];
					for (int i = 1; i < ks; i++) {
						if (bn[i] < enk)
							enb = bn[i];
					}
					System.out.println("En büyük Küçük notu : " + enk);

					break;
				case 5:int bnt = 0;
				for (int i = 0; i < ks; i++) {
					bnt+=bn[i];
				}
				System.out.println("Başarı Not ortalaması : "+(bnt/ks));

					break;
				case 6:
					System.out.println("program bitti");
					System.exit(0);

					break;

				default:
					break;
				}
			}

		}

	}//kişinin adı , kaç dakika , sms , internet ne kadar kullandığını giricek dikika 70 kuruş sms 55 krş internet 1gb 15 tl fatura hesapla üstüne yüzde 25 vergi 1 - listeleme 2- isim arama - 3dakika sms internet fatura ort 4- fatura enk kime ait ve her birinin en büyüğü ve çıkış
}
