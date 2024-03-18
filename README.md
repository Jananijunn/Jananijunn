class Organization implements Cloneable {
    private int organizationCode;
    private String organizationName;
    private String organizationAddress;

    
    public Organization(int code, String name, String address) {
        this.organizationCode = code;
        this.organizationName = name;
        this.organizationAddress = address;
    }

    
    public void printDetails() {
        System.out.println("Organization Code: " + organizationCode);
        System.out.println("Organization Name: " + organizationName);
        System.out.println("Organization Address: " + organizationAddress);
    }

    
    @Override
    public Organization clone() throws CloneNotSupportedException {
        return (Organization) super.clone();
    }
}

public class Main {
    public static void main(String[] args) {
        
        Organization org1 = new Organization(1, "ABC Corp", "123 Main St");

      
        try {
            Organization org2 = org1.clone();

            // Printing details of original and cloned objects
            System.out.println("Original Object:");
            org1.printDetails();

            System.out.println("\nCloned Object:");
            org2.printDetails();
        } catch (CloneNotSupportedException e) {
            e.printStackTrace();
        }
    }
}
