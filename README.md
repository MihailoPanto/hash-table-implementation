# Hash Table Implementation

A hash table implemented in C++ with bucket-based storage and double hashing for collision resolution. Records store student data (index number, name, and subjects).

## Features

- **Bucket hash table** — each slot holds multiple entries (configurable bucket capacity)
- **Double hashing** — open addressing collision resolution using a secondary hash function: `h(k, i) = (h(k) + i * (q + k % p)) % n`
- **CSV file loading** — populate the table from a file
- **Interactive menu** — console-driven interface for all operations

## Data Structure

Each record (`Info`) stores:
- `key` — student index number (unsigned integer)
- `name` — student name
- `subjects` — list of enrolled subjects (up to 10)

## Building

Requires a C++11 compiler. Open `dz3asp.sln` in Visual Studio, or compile manually:

```bash
g++ -std=c++11 Source.cpp -o hashtable
./hashtable
```

## Usage

On startup, first create a new hash table (option 1), then use the menu to interact with it:

| Option | Description |
|--------|-------------|
| 1 | Create new hash table |
| 2 | Load students from CSV file |
| 3 | Insert a student manually |
| 4 | Find a student by key |
| 5 | Delete a student by key |
| 6 | Clear the table |
| 7 | Print key count |
| 8 | Print table size (number of buckets) |
| 9 | Print the full table |
| 10 | Print fill ratio |
| 0 | Exit |

### Hash Table Parameters (option 1)

- **Bucket size** — number of entries per bucket
- **p (index bits)** — number of bits for table indexing; table size = 2^p
- **p, q** — parameters for the secondary hash function

### CSV File Format (option 2)

```
header_line
key,Name Surname,subject1 subject2 subject3
```

Example:
```
index,name,subjects
12345,Petar Petrovic,Math Physics OOP
```
