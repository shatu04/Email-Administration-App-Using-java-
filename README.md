# 📧 Email Administration App (Java)

This is a simple **Email Administration Application** built using Java.  
It simulates how a company might automatically generate and manage employee email accounts.

---

## 🚀 Features
- Generate a company email ID based on:
  - First Name
  - Last Name
  - Department (Sales, Development, Accounting, or None)
- Generate a **random secure password** (default length = 12 characters)
- Set and update:
  - Mailbox capacity
  - Alternate email
  - Password
- Display employee details (name, email, mailbox capacity)

---

## 🛠 Technologies Used
- Java (Core Java, OOP concepts)
- Scanner (for input handling)

---

## 📂 Project Structure
<img width="517" height="197" alt="image" src="https://github.com/user-attachments/assets/9ade190b-cf68-437b-be78-2dea655cb6df" />


---

## ▶️ How to Run
## 1. IN CMD 


---

### ✅ Step 1: Save Your Project

Make sure your folder structure looks like this:

```
EmailAdministrationApp/
├── src/
│   └── emailapp/
│       ├── Email.java
│       └── EmailApp.java
```

---

### ✅ Step 2: Open Command Prompt

1. Press `Win + R`, type `cmd`, hit **Enter**.
2. Navigate to your project folder (where `src` is located). Example:

   ```cmd
   cd Desktop\EmailAdministrationApp\src
   ```

---

### ✅ Step 3: Compile the Java Files

Compile both `.java` files inside the `emailapp` package:

```cmd
javac emailapp\*.java
```

👉 This will create `.class` files inside the same `emailapp` folder.

---

### ✅ Step 4: Run the Program

Now run the main class (`EmailApp`):

```cmd
java emailapp.EmailApp
```

---

### ✅ Example Execution

```cmd
C:\Users\YourName\Desktop\EmailAdministrationApp\src> javac emailapp\*.java

C:\Users\YourName\Desktop\EmailAdministrationApp\src> java emailapp.EmailApp
New Worker: Shatavari Birajdar 
 Department Codes:
0 for none
1 for Sales
2 for Development
3 for Accounting
Enter the department code: 2

DISPLAY NAME: Shatavari Birajdar
COMPANY EMAIL: shatavari.birajdar@dev.smbcompany.com
MAILBOX CAPACITY: 500mb
```

---

⚡ That’s it! Your app should now work from the command line.

## 2 IN ECLIPS 


---

## ✅ Step 1: Open Eclipse & Create a New Project

1. Open **Eclipse IDE**.
2. Go to the top menu → **File → New → Java Project**.
3. Enter project name → `EmailAdministrationApp`.
4. Click **Finish**.

---

## ✅ Step 2: Create the Package

1. In the **Project Explorer**, expand your project.
2. Right-click on `src` → **New → Package**.
3. Enter package name: `emailapp`.
4. Click **Finish**.

---

## ✅ Step 3: Add Java Files

1. Right-click on the package `emailapp` → **New → Class**.

   * Name it `Email`.
   * Paste the `Email.java` code inside.
2. Again, right-click on the package `emailapp` → **New → Class**.

   * Name it `EmailApp`.
   * Paste the `EmailApp.java` code inside.

---

## ✅ Step 4: Run the Application

1. In the Project Explorer, right-click on `EmailApp.java`.
2. Select **Run As → Java Application**.
3. The **Console window** at the bottom will show your program running.

---

## ✅ Example Output (inside Eclipse console)

```
New Worker: Shatavari Birajdar 
Department Codes:
0 for none
1 for Sales
2 for Development
3 for Accounting
Enter the department code: 2

DISPLAY NAME: Shatavari Birajdar
COMPANY EMAIL: shatavari.birajdar@dev.smbcompany.com
MAILBOX CAPACITY: 500mb
```

---

⚡ That’s it! Your app now runs smoothly in Eclipse.

## 3 IN VS CODES 

---

## ✅ Step 1: Install Java & VS Code Extensions

1. Make sure **Java JDK** is installed.

   * Check in terminal:

     ```bash
     java -version
     javac -version
     ```
   * If not installed, download [JDK 17](https://adoptium.net/) or later.

2. In **VS Code**, install these extensions:

   * **Extension Pack for Java** (Microsoft)
   * **Debugger for Java**
   * **Java Test Runner**

---

## ✅ Step 2: Set Up Folder Structure

Create a folder like this on your system:

```
EmailAdministrationApp/
└── src/
    └── emailapp/
        ├── Email.java
        └── EmailApp.java
```

Open the **`EmailAdministrationApp`** folder in VS Code.

---

## ✅ Step 3: Add Code

1. Inside `src/emailapp/Email.java`, paste:

   ```java
   package emailapp;

   import java.util.Scanner;

   public class Email {
       private String firstName;
       private String lastName;
       private String password;
       private String department;
       private String alternateEmail; 
       private String email;
       private String companySffix = "smbcompany.com"; 
       private int mailboxcapacity = 500;
       private int defaultPasswordLength = 12;
       private int setMailboxCapacity;

       public Email(String firstName, String lastName) { 
           this.firstName = firstName;
           this.lastName = lastName;
           this.department = setDepartment();
           this.password = randomPassword(defaultPasswordLength);
           email = firstName.toLowerCase() + "." + lastName.toLowerCase() + 
                   "@" + department + "." + companySffix;
       }

       private String setDepartment() {
           System.out.println("New Worker: " + firstName + " " + lastName +  
                              " Department Codes:\n0 for none\n1 for Sales\n2 for Development\n3 for Accounting\nEnter the department code: ");
           Scanner in = new Scanner(System.in);
           int depChoice = in.nextInt();
           if (depChoice == 1) return "sales";
           else if (depChoice == 2) return "dev";
           else if (depChoice == 3) return "acct";
           else return "";
       }

       private String randomPassword(int length) {
           String passwordSet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%";
           char[] password = new char[length];
           for (int i=0; i<length; i++) {
               int rand = (int) (Math.random() * passwordSet.length());
               password[i] = passwordSet.charAt(rand);
           }
           return new String(password);
       }

       public void setMailboxCapacity(int capacity) { this.setMailboxCapacity = capacity; }
       public void setAlternateEmail(String altEmail) { this.alternateEmail = altEmail; }
       public void changePassword(String password) { this.password = password; }

       public int getMailboxCapacitty() { return mailboxcapacity; }
       public String getAlternateEmail() { return alternateEmail; }                                                                                 
       public String getPassword() { return password; }

       public String showInfo() {
           return "DISPLAY NAME: " + firstName + " " + lastName +
                  "\nCOMPANY EMAIL: " + email +
                  "\nMAILBOX CAPACITY: " + mailboxcapacity + "mb";
       }
   }
   ```

2. Inside `src/emailapp/EmailApp.java`, paste:

   ```java
   package emailapp;

   public class EmailApp {
       public static void main(String[] args) {
           Email em1 = new Email("Shatavari", "Birajdar"); 
           System.out.println(em1.showInfo());
       }
   }
   ```

---

## ✅ Step 4: Run in VS Code

1. Open the **Command Palette** (`Ctrl+Shift+P` or `F1`).
2. Search → **Java: Configure Java Runtime** → ensure JDK is selected.
3. Open `EmailApp.java`.
4. On the top-right, click the green **Run ▶️ button**.

   * OR right-click inside `main()` → **Run Java**.

---

## ✅ Step 5: Output in VS Code Terminal

```
New Worker: Shatavari Birajdar 
Department Codes:
0 for none
1 for Sales
2 for Development
3 for Accounting
Enter the department code: 2

DISPLAY NAME: Shatavari Birajdar
COMPANY EMAIL: shatavari.birajdar@dev.smbcompany.com
MAILBOX CAPACITY: 500mb
```

---

⚡ Done! Your app is running inside **VS Code** 🎉

📝 Future Enhancements

Add GUI interface (JavaFX or Swing)

Store employee records in a database

Provide email sending/receiving simulation


