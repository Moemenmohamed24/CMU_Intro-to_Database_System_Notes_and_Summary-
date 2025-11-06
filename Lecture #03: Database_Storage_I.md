# DISK-BASED ARCHITECTURE

<img width="646" height="374" alt="image" src="https://github.com/user-attachments/assets/0e80df07-e00b-4590-8233-4db9958aa6bc" />

# What is CXL?:

CXL stands for Compute Express Link. It's a very modern interconnect protocol developed to speed up communication between:
• The CPU (Central Processing Unit)
• and other devices such as GPUs, memory expanders, or accelerators.

CXL was designed to solve speed, latency, and compatibility issues that systems faced when adding hardware.

<img width="903" height="311" alt="image" src="https://github.com/user-attachments/assets/615c138b-1e75-480f-8922-f9cb9edd48b0" />

# ACCESS TIMES:

<img width="1199" height="678" alt="Screenshot 2025-10-30 233523" src="https://github.com/user-attachments/assets/411f621a-3a37-454c-a9af-7eca04c211c8" />


# SEQUENTIAL VS. RANDOM ACCESS

Sequential Access in Databases/Storage :
Better for large writes or massive data transfers.
Example: If you're going to record millions of rows at once in a table, sequential writes are faster because they write the data sequentially to the disk or SSD.
On a tape or HDD, sequential writes are much faster than random access.

Random Access in Databases/Storage :
Best for reading or updating individual data.
Example: If you want to retrieve a single row or modify a specific value in a table, random access is much faster because it doesn't need to iterate through all the data beforehand.
RAM and SSD are excellent for fast random access.

Using Both Together :
Database systems use sequential data storage in large files or logs.
They use random access to individual rows via indexes.
The idea: To take advantage of the combined speed of sequential writes and random reads.



# (Disk-Oriented DBMS):

<img width="842" height="376" alt="image" src="https://github.com/user-attachments/assets/2e6d9494-1a0c-4b0b-a5ac-28568f128852" />


# FILE STORAGE :

<img width="1205" height="681" alt="Screenshot 2025-11-06 163406" src="https://github.com/user-attachments/assets/a9ff46b7-6868-4b40-8022-b3806b4ab849" />





