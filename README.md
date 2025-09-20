

## File Encryptor & Decryptor

Author: Nishtha Dahiya.
Language: C++
Project Type: Systems Programming / File Security.

⸻

## #Table of Contents
	•	Introduction
	•	Project Motivation
	•	Features
	•	System Components Used
	•	Working Flow
	•	Diagrams for easy understanding
	•	Limitations
	•	Potential Extensions
	•	Project Files
	•	How to Run 

⸻

## Introduction

This project implements a File Encryption and Decryption system using process management and inter-process communication techniques.

## Key objectives:
	•	Securely encrypt and decrypt files using a key from a .env file.
	•	Handle multiple files in a directory via a task queue.
	•	Demonstrate multiprocessing, semaphores, and synchronization techniques.
	•	Implement modular design with reusable components for file I/O, process handling, and cryptographic logic.

⸻

## Project Motivation

The project was built to:
	•	Explore low-level file handling in C++..
	•	Understand process creation (fork, exec) and management.
	•	Apply synchronization techniques such as semaphores and locks.
	•	Create a practical project that can encrypt/decrypt multiple files efficiently.
<img width="928" height="635" alt="Screenshot 2025-09-12 at 9 12 00 PM" src="https://github.com/user-attachments/assets/82442170-322f-4832-ba81-43e99e36746a" />

⸻

 ## Features
	•	File-based encryption & decryption with a configurable key stored in .env.
	•	Process queue management for handling multiple tasks.
	•	Multiprocessing (fork & exec) to run encryption/decryption in separate processes.
	•	Error handling for invalid input, file access errors, or missing keys.
	•	Custom task management system (Task objects with serialization/deserialization).
	•	Supports batch encryption/decryption of all files inside a directory.

⸻

## System Components Used
	•	Processes: Created using fork() and exec() for parallel execution.
	•	Semaphores & Locks: To synchronize access when multiple processes run.
	•	File I/O: Custom IO class for managing file streams.
	•	Environment Loader: Reads encryption key from .env.
	•	Task Queue: Stores encryption/decryption jobs.
	•	Makefile: Automates compilation of project binaries.

⸻

## Working Flow
	1.	User specifies a directory path and action (encrypt/decrypt).
	2.	The system scans all files in the directory.
	3.	Each file is wrapped into a Task object with metadata.
	4.	Tasks are pushed into a queue.
	5.	Process Management executes tasks one by one (or via child processes).
	6.	Files are modified in-place with encryption/decryption applied.

⸻

## Diagrams

UML diagram 
<img width="688" height="427" alt="Screenshot 2025-09-12 at 9 11 17 PM" src="https://github.com/user-attachments/assets/fbbb779f-f60b-4227-9797-ca6ab7203312" />

TERMINAL OUTPUT 
<img width="1470" height="956" alt="Screenshot 2025-09-12 at 9 09 51 PM" src="https://github.com/user-attachments/assets/994deae6-c0c4-4bdc-9ec9-945f1cc5d1c7" />

Encrypted text: 

<img width="1470" height="956" alt="Screenshot 2025-09-12 at 9 07 41 PM" src="https://github.com/user-attachments/assets/c9780a50-63b8-4f06-8652-85570f4f558a" />
____

##  Limitations
	•	Only supports basic Caesar-like shift encryption (not cryptographically secure).
	•	Requires .env file containing the numeric key.
	•	Encryption modifies files in-place (no backup).
	•	Currently sequential execution (multiprocessing code included but commented for testing).

⸻

## Potential Extensions
	•	Add advanced cryptography algorithms (AES, RSA).
	•	Implement multithreading instead of forking.
	•	Add logging system for tracking tasks.
	•	Support file backups before modification.
	•	Add a GUI frontend for user interaction.

⸻

## Project Files
	•	main.cpp – Entry point of the program.
	•	src/file/ – File I/O and environment variable handling.
	•	src/processes/ – Process management and task queue.
	•	src/encryptdecrypt/ – Encryption/Decryption logic.
	•	Makefile – Build automation.
	•	.env – Stores encryption key.

⸻

## How to Run

1. Clone Repository

git clone <repo-link>
cd File-Encryptor-Decryptor

2. Build Project

make all

3. Run Encryption/Decryption

./encrypt_decrypt

Enter the directory path and action (encrypt/decrypt) when prompted.

4. Run Cryption Executable Directly

./cryption "filename.txt,ENCRYPT"


⸻

## Example
	•	Input file: test1.txt → HELLO WORLD!
	•	Key in .env: 1234
	•	After encryption: scrambled binary data.
	•	After decryption: restored to HELLO WORLD!.

⸻

## License

MIT License

⸻

👉 This README makes the project look serious and systems-level, not just “basic.”

Do you want me to also create diagrams (system flow/UML) for this project so you can directly add them to GitHub like you did in your Proxy Server repo?
