# HDLC Protocol Simulation in Java
This project is a simulation of a simplified HDLC (High-Level Data Link Control) protocol implemented in Java. It demonstrates reliable data transmission between a sender and receiver using features such as Go-Back-N, bit stuffing, and CRC (Cyclic Redundancy Check) for error detection.

## Features
- ### HDLC Protocol Simulation:
  - Unidirectional communication between sender and receiver.
  - Simulates reliable data transfer with acknowledgments (ACK) and negative acknowledgments (NACK).

- ### Error Detection:
  - Implements CRC-CCITT (16-bit polynomial) for error detection.
  - Introduces bit stuffing for frame data.

- ### Frame Management:
  - Supports connection, information, acknowledgment, and termination frames.
- ### Customizable Tests:
  - Allows simulating transmission errors, such as bit flips or frame loss.

## Project Structure
### Main Components
1. ```Sender.java```:
  - Reads data from an input file and sends frames to the receiver.
  - Handles connection setup, frame transmission, acknowledgments, and retransmissions.
  - Implements Go-Back-N for managing a sliding window.

2. ```Receiver.java```:
  - Receives frames from the sender and processes them.
  - Detects errors using CRC and sends appropriate acknowledgments (ACK or NACK).
  - Writes successfully received data to an output file.

3. ```Frame.java```:
  - Represents a communication frame with fields for type, number, data, and CRC.
  - Provides methods for constructing, parsing, and validating frames.

4. ```FrameType.java```:
  - Utility class for creating specific types of frames (e.g., ACK, NACK, information, connection, and termination).

5. ```CRC.java```:
  - Implements CRC-CCITT (x16 + x12 + x5 + 1) for error detection.
  - Provides methods for calculating and validating CRC checksums.

6. ```Flag.java```:
  - Implements bit stuffing and de-stuffing for frame data.

7. ```IOFile.java```:
  - Handles reading input data and writing output data to files.

8. ```test.java```:
  - Includes test cases for validating individual classes and methods.

### Input/Output Files
  - ```in.txt```: Input data file containing lines to be transmitted by the sender.
  - ```out.txt```: Output data file where the receiver writes successfully received data.

### Error Simulation
A separate class introduces transmission errors to simulate real-world network conditions, such as:
- Bit flipping in frames.
- Frame loss.
- Acknowledgment loss.

## How to Run
### Prerequisites
- Java Development Kit (JDK) installed.
- Compatible with Linux-based systems, as required by the DIRO environment.

## Compilation
Compile all Java files using the following command:

```javac *.java```

## Running the Sender
```java Sender <Receiver_Host> <Port_Number> <Input_File> <Mode>```

- Mode: Set to 0 for Go-Back-N.

Example:
```java Sender localhost 8080 in.txt 0```

## Running the Receiver
```java Receiver <Port_Number>```

Example:
```java Receiver 8080```

## Testing
Run the ```test.java ```file to validate the functionality of individual components:

```java test```

## Class Diagram
Refer to the accompanying report (```rapport.pdf```) for the class diagram and detailed explanations of the design and methods.

## Authors
- Lucky Khounvongsa (20172476)
- Walid Boudehane (20206664)
