
### Table of content
- [Overview](#overview)
- [Core functionality](#core-functionality)
- [UML Class Diagram](#uml-class-diagram)
- [Running Instructions](#running-instructions)
  - [Desktop App](#desktop-app)
  - [Client-Server Model](#client-server-model)

## **Overview**

This API provides a robust solution for converting CSV files to XML and vice versa. It also supports data validation during the conversion process. Whether you’re working with embedded implementations or need a more advanced client-server architecture, this API is designed to adapt to your use case.

### **Key Features**

- **Bidirectional Conversion**: Seamlessly convert between CSV and XML formats.
- **Validation Support**: Perform data validation before writing to the output file.
- **Custom DTO Support**: Easily define your own data transfer objects with standard getter/setter methods.
- **Flexible Integration**: Use as a desktop application or via client-server architecture.
- **Built-in Object Creator**: Automatically populates DTOs from source files (supports String fields).

## **Core Functionality**
This repository includes all necessary dependencies for running the converter.

If your workflow requires transforming XML data into CSV (or vice versa) with validation steps in between, this API streamlines the entire process. It reads input data, maps it to objects, validates it based on rules you define, and writes the validated data to a new file format.

**Conversion Workflow**

- Read Data: Extract data from the input file (CSV/XML).
- Create DTOs: Map data into user-defined DTOs using the Object Creator service.
- Validate Data: Apply validation using built-in or custom rules.
  - Exclude Validator: Skips invalid records.
  - Exception Validator: Stops the process on validation failure.
- Write Data: Output the validated records into a new file (CSV or XML).

Note: The Object Creator currently supports only DTOs with String-type fields and standard getter/setter methods.

Additionally, if you need to rearrange or reformat data within the same file type, this API supports that as well.

## **UML Class Diagram**

A UML class diagram is provided to help you better understand the architecture and data flow.

![Class diagram](https://github.com/user-attachments/assets/9eb726b8-45d8-4800-a6b6-0d29c1cd1434)

## **Running Instructions**

This project includes two applications:

- Swing Desktop Application
- Client-Server Application

Both can be executed via the JAR files available in the <code>runningJars/</code> folder.

### **Desktop App**

To use the Swing demo application:

-  Option 1: Clone the repository.
-  Option 2: Download the executable JAR file (click "View raw" to download).

Locate the desktop JAR in <code>runningJars/desktopApp</code> and run the application with the following command:

```bash
java -jar application_1.jar /input/dir/path/ /output/dir/path/
```

<code>/input/dir/path/</code>: Directory containing your XML and/or CSV files.

Sample files are available in <code>sample/input</code>.

### **Client-Server Model**

This model consists of a server component and a client component.

- Important: Start the server before starting the client.

1. Start the Server using command:

```bash
java -jar server_app.jar 1234 /output/dir/path/output_file_name.xml
```

- Replace 1234 with the desired port number.
- Specify the output file name and format (e.g., .xml or .csv).

2. Start the Client using command:

```bash
 java -jar client_app.jar localhost 1234 /input/dir/path/input_file.xml
```

- Ensure the port number matches the server.
- Input files should be located in the specified input path. Sample files are provided in <code>sample/input</code>.
