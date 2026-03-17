package com.seed;

import com.seed.service.InstituteService;
import java.util.Scanner;

public class App {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        InstituteService service = new InstituteService();

        while (true) {
            System.out.println("\n1. Save Data");
            System.out.println("2. Fetch Data");
            System.out.println("3. Exit");

            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    service.saveInstitute();
                    break;

                case 2:
                    System.out.println("Enter Institute ID:");
                    int id = sc.nextInt();
                    service.getInstitute(id);
                    break;

                case 3:
                    System.exit(0);

                default:
                    System.out.println("Invalid choice");
            }
        }
    }
}
