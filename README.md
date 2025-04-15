import java.util.Scanner;

class Transport {
    private String model;
    private int maxSpeed;
    private String energySource;
    public Transport(String model, int maxSpeed, String energySource) {
        this.model = model;
        this.maxSpeed = maxSpeed;
        this.energySource = energySource;
    }

    public String getModel() {
        return model;
    }
public int getMaxSpeed() {
        return maxSpeed;
    }

    public String getEnergySource() {
        return energySource;
    }

    public void showDetails() {
        System.out.println("Model: " + model);
        System.out.println("Top Speed: " + maxSpeed + " km/h");
        System.out.println("Energy Source: " + energySource);
    }
}

class Sedan extends Transport {
    private int doorCount;

    public Sedan(String model, int maxSpeed, String energySource, int doorCount) {
        super(model, maxSpeed, energySource);
        this.doorCount = doorCount;
    }

    @Override
    public void showDetails() {
        super.showDetails();
        System.out.println("Door Count: " + doorCount);
    }
}
class Bike extends Transport {
    private boolean sidecarAttached;

    public Bike(String model, int maxSpeed, String energySource, boolean sidecarAttached) {
        super(model, maxSpeed, energySource);
        this.sidecarAttached = sidecarAttached;
    }

    @Override
    public void showDetails() {
        super.showDetails();
        System.out.println("Sidecar Attached: " + (sidecarAttached ? "Yes" : "No"));
    }
}

public class VehicleTestDrive {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.println("Enter Sedan Info:");
        System.out.print("Model: ");
        String sedanModel = input.nextLine();
        System.out.print("Top Speed (km/h): ");
        int sedanSpeed = input.nextInt();
        input.nextLine();
        System.out.print("Energy Source: ");
        String sedanFuel = input.nextLine();
        System.out.print("Number of Doors: ");
        int sedanDoors = input.nextInt();
        input.nextLine();

        Sedan sedan = new Sedan(sedanModel, sedanSpeed, sedanFuel, sedanDoors);

        System.out.println("\nEnter Bike Info:");
        System.out.print("Model: ");
        String bikeModel = input.nextLine();
        System.out.print("Top Speed (km/h): ");
        int bikeSpeed = input.nextInt();
        input.nextLine();
        System.out.print("Energy Source: ");
        String bikeFuel = input.nextLine();
        System.out.print("Sidecar Attached (true/false): ");
        boolean bikeSidecar = input.nextBoolean();

        Bike bike = new Bike(bikeModel, bikeSpeed, bikeFuel, bikeSidecar);

        System.out.println("\nSedan Information:");
        sedan.showDetails();

        System.out.println("\nBike Information:");
        bike.showDetails();

        input.close();
    }
}
