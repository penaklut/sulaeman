import java.util.ArrayList;
import java.util.Scanner;

public class TaskTracker {
    public static void main(String[] args) {
        ArrayList<String> tasks = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        boolean running = true;

        System.out.println("=== Java Task Tracker Simple ===");

        while (running) {
            System.out.println("\n1. Tambah Tugas");
            System.out.println("2. Lihat Tugas");
            System.out.println("3. Keluar");
            System.out.print("Pilih opsi: ");

            String choice = scanner.nextLine();

            switch (choice) {
                case "1":
                    System.out.print("Masukkan nama tugas: ");
                    String task = scanner.nextLine();
                    tasks.add(task);
                    System.out.println("Tugas berhasil ditambahkan!");
                    break;
                case "2":
                    System.out.println("\nDaftar Tugas Anda:");
                    if (tasks.isEmpty()) {
                        System.out.println("(Belum ada tugas)");
                    } else {
                        for (int i = 0; i < tasks.size(); i++) {
                            System.out.println((i + 1) + ". " + tasks.get(i));
                        }
                    }
                    break;
                case "3":
                    running = false;
                    System.out.println("Terima kasih telah menggunakan aplikasi!");
                    break;
                default:
                    System.out.println("Opsi tidak valid.");
            }
        }
        scanner.close();
    }
}
