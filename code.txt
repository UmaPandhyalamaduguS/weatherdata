import java.util.Scanner;


public class Myclass {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        WeatherAPI w = new WeatherAPI();

        int A;
        do {
            Menu();
            A = scanner.nextInt();
            scanner.nextLine();

            switch (A) {
                case 1:
                    System.out.print("Enter the date (YYYY-MM-DD): ");
                    String date = scanner.nextLine();
                    double Temperature = w.getTemp(date);
                    System.out.println("Temperature on " + date + ": " + Temperature + "°C");
                    break;

                case 2:
                    System.out.print("Enter the date (YYYY-MM-DD): ");
                    date = scanner.nextLine();
                    double WindSpeed = w.getWindSpeed(date);
                    System.out.println("Wind Speed on " + date + ": " + WindSpeed + " m/s");
                    break;

                case 3:
                    System.out.print("Enter the date (YYYY-MM-DD): ");
                    date = scanner.nextLine();
                    double Pressure = w.getPressure(date);
                    System.out.println("Pressure on " + date + ": " + Pressure + " hPa");
                    break;

                case 0:
                    System.out.println("Terminating the program. Goodbye!");
                    break;

                default:
                    System.out.println("Invalid option. Please try again.");
            }
        } while (A != 0);

        scanner.close();
    }

    private static void Menu() {
        System.out.println("Choose an option from below:");
        System.out.println("1. Get Temperature");
        System.out.println("2. Get Wind Speed");
        System.out.println("3. Get Pressure");
        System.out.println("0. Exit");
    }
}

class WeatherAPI {
    public double getTemp(String date) {
        return 281.5;
    }

    public double getWindSpeed(String date) {
        return 5.0;
    }

    public double getPressure(String date) {
        return 1021.88;
    }
}