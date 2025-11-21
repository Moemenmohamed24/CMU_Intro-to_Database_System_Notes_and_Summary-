<img width="669" height="758" alt="image" src="https://github.com/user-attachments/assets/8d0a8698-86c8-484a-91c6-89a234d0e319" /># RECORD IDS :

<img width="897" height="508" alt="Screenshot 2025-11-10 135903" src="https://github.com/user-attachments/assets/a1a1808d-4d21-438e-937d-5769887d1d69" />


# TUPLE-ORIENTED STORAGE :
 
<img width="634" height="320" alt="image" src="https://github.com/user-attachments/assets/3c87be0c-b912-4677-9c10-b9dd2a143baf" />

# Problems TUPLE-ORIENTED STORAGE :

<img width="681" height="395" alt="image" src="https://github.com/user-attachments/assets/7d0ce88b-6d04-4953-8eef-03e954f09a39" />

LOG-STRUCTURED STORAGE:

<img width="752" height="375" alt="image" src="https://github.com/user-attachments/assets/3c0fa52c-9e60-4ee5-8835-9f4d3d6d03aa" />

Internal Structure: MemTable + SSTable

The LSM Tree mainly operates on two levels:

A. MemTable (Memory)

All new updates are first applied to a data structure in memory.

Usually a Sorted Map or Tree like Red-Black Tree or Skip List.

Every PUT/DELETE operation goes directly into the MemTable → very fast because it’s in RAM.

Every log entry is also written to the Write-Ahead Log (WAL) to ensure no data loss in case of a crash.

B. SSTable (Disk)

When the MemTable fills up, it is flushed to disk sequentially as an SSTable.

Each SSTable is an immutable file on disk containing data sorted by key.

Existing SSTables are not modified; a new one is created when merging data.

 Compaction Process

Over time, old SSTables accumulate.
The DBMS performs compaction:

Merges multiple SSTable files into a new single file.

Deletes obsolete rows (DELETE) or old versions (previous UPDATE).

Keeps the data sorted.

Goal: Reduce space usage and improve read speed.

✅ Advantages of Log-Structured Storage

Sequential writes to disk → very high write performance.

Crash-safe: every operation is recorded in the WAL.

Scalable: data can easily be split across multiple files/disks.

Version history preserved: possible to reconstruct any version of data from logs.

⚠️ Disadvantages

Random reads are less efficient: data spread across multiple SSTables → may require searching in several files.

Temporary extra space: due to old files before compaction.

Continuous maintenance required: compaction can sometimes be expensive.
# LOG-STRUCTURED STORAGE :

<img width="519" height="376" alt="image" src="https://github.com/user-attachments/assets/a36a54a3-f25b-43f7-aef7-78c8014bf4dd" />

### Summary Table (Simplified Explanation)

The **SummaryTable** doesn’t perform the search itself.
Instead, it acts as a **smart index or guide** that the system uses to quickly determine **where to look** inside the SSTables on disk.

In other words:
The **SummaryTable** doesn’t contain the actual values — it only holds **metadata** that helps the system decide:

> “Which SSTable file should I open and search in?”

---

###  Let’s break down the process step by step:

####  Search in Memory (MemTable)

First, the system checks if the key exists in the **MemTable**.

* If it’s found → the value is returned immediately.
* If it’s not found → the system moves to the next step.

---

####  Search in the SummaryTable

Instead of opening every file on disk (which would be very slow),
the system looks into the **SummaryTable** stored in memory. It contains:

* The **Min Key / Max Key** for each SSTable → defines the range of keys inside each file.
* A **Key Filter** (like a **Bloom Filter**) → quickly tells whether a key *might* be in that file or *definitely not*.

**Example:**
If the key you’re looking for is `key101`, and the SummaryTable says:

* SSTable 1 → keys 1–50
* SSTable 2 → keys 51–150
* SSTable 3 → keys 151–300

Then the system instantly knows it should **search only in SSTable #2**.

---

####  Search inside the SSTable (on Disk)

After identifying the right file using the SummaryTable:

* The system opens **SSTable #2**.
* Performs a **binary search** inside it (since it’s sorted).
* Finds and returns the desired value.


# DATA LAYOUT:

<img width="669" height="758" alt="Screenshot 2025-11-21 181726" src="https://github.com/user-attachments/assets/74c086f3-00b0-4e3e-ad00-91a83bbb7102" />







