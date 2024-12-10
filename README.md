import java.util.Scanner;
public class PsychologySurvey {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("ّFullName: ");
        String fullName = scanner.nextLine();
        System.out.print("Age: ");
        int age = scanner.nextInt();
        scanner.nextLine(); 
        System.out.print("DoctorName: ");
        String doctorName = scanner.nextLine();
        System.out.print("Reference date: (for example: 1403/01/01)");
        String visitDate = scanner.nextLine();
        int totalScore = 0;
        String[] questions = {
            "َAya ehsas khoshali mikonid? (Yes/No)",
            "Aya khabe kafi darid? (Yes/No)",
            "Aya be khodetan etemad darid? (Yes/No)",
            "Aya ehsas tanesh  darid? (Yes/No)",
            "Aya az faaliat hay rozmare khod razii hastid?(Yes/No)"
        };
        int[] scores = {20, 20, 20, 0, 20}; 
        for (int i = 0; i < questions.length; i++) {
            System.out.print(questions[i] + " ");
            String answer = scanner.nextLine().toLowerCase();
            if (answer.equals("yes")) {
                totalScore += scores[i];
            } else if (answer.equals("no")) {
                totalScore += (scores[i] == 0 ? 0 : 0); 
            } else {
                System.out.println("pasokh namotabar. lotfan (Yes/No)");
                i--; 
            }
        }
        System.out.println("\nnatije:");
        System.out.println("FullName: " + fullName);
        System.out.println("Age: " + age);
        System.out.println(" DoctorName: " + doctorName);
        System.out.println(" Reference date:: " + visitDate);
        System.out.println("Final Score: " + totalScore);
        if (totalScore >= 80) {
            System.out.println("tosie: vazeiat ravani khobi darid.");
        } else if (totalScore >= 40) {
            System.out.println("tosie: momkan ast be moshavere niaz dashte bashid.");
        } else {
            System.out.println("tosie: behtar ast ba motekhases mashverat konid.");
        }
        scanner.close();
    }
}

