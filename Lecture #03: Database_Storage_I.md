<img width="719" height="368" alt="image" src="https://github.com/user-attachments/assets/85c65089-77f9-4911-9062-ca6704b5941c" /><img width="790" height="352" alt="image" src="https://github.com/user-attachments/assets/00f07b2f-cc29-432a-9727-51614ba51eb8" /># DISK-BASED ARCHITECTURE

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


# Storage Manager :
<img width="790" height="352" alt="image" src="https://github.com/user-attachments/assets/c7755279-2621-4ef5-ad4a-359ea7a20f8c" />



# Database Page :

<img width="865" height="325" alt="image" src="https://github.com/user-attachments/assets/6000f0ba-12b2-4127-99d7-011a5a68d6e4" />

<img width="760" height="357" alt="image" src="https://github.com/user-attachments/assets/2530dbd4-4c02-4124-b13e-e41eca3ad457" />

# PAGE STORAGE ARCHITECTURE :

<img width="1204" height="669" alt="Screenshot 2025-11-06 213749" src="https://github.com/user-attachments/assets/f804af63-6c39-4b69-a50e-b0bf07ba23de" />


# HEAP FILE :
<img width="1192" height="679" alt="image" src="https://github.com/user-attachments/assets/7cc86ef8-4aa2-4d92-a5e0-e14ae172c212" />

# Multy HEAP FILE :
<img width="757" height="322" alt="image" src="https://github.com/user-attachments/assets/a5cd7c5f-1c1e-49e2-b8cf-7c748c35379f" />



# HEAP FILE – PAGE DIRECTORY :

<img width="975" height="547" alt="image" src="https://github.com/user-attachments/assets/b4afcdc7-7168-46f6-b30f-28a24d84c483" />

# PAGE HEADER :

<img width="1200" height="678" alt="Screenshot 2025-11-07 213644" src="https://github.com/user-attachments/assets/28ec7b7f-e5c3-4b79-8e87-af67cb3d606f" />

What is a Page Header?

Every database page has a small section at the beginning called the Page Header.
This section contains information about the page itself, not the data within it.
# PAGE LAYOUT :

<img width="719" height="368" alt="image" src="https://github.com/user-attachments/assets/cc94f682-ae1c-4bc1-9011-cfaa3407c9f1" />

