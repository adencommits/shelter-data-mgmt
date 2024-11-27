### Lab 6: Shelter Data Management with Linked Lists

**Project Overview:**

This project implements a linked list data structure to organize and manage shelter information for the Greater Toronto Area (GTA). It processes data regarding the number of occupied and unoccupied beds at various shelters, and provides functionalities to calculate occupancy rates and find shelters serving specific population sectors, such as "Men", "Women", and "Youth."

---

**Key Features:**

- **Linked List Implementation:** A custom linked list is used to store `Shelter` objects, where each shelter contains information about its name, sector, and bed occupancy.
  
- **Occupancy Rate Calculation:** The program calculates the occupancy rate of the shelters in the list, with the option to filter by sector (e.g., "Women", "Men", "Youth").

- **Sector Indexing:** The program allows searching for the first occurrence of a shelter serving a specified sector.

- **CSV Data Parsing:** Shelter data is read from a CSV file and converted into `Shelter` objects, which are then stored in the linked list.

---

**Classes in the Project:**

1. **Shelter Class:** 
   - Stores information about each shelter, including the name, sector served, and the number of occupied and unoccupied beds.

2. **LinkedList Class:** 
   - Implements a linked list to store `Shelter` objects and provides methods to interact with the shelter data, such as calculating occupancy rates and indexing sectors.

3. **Node Class:** 
   - Represents a node in the linked list. Each node contains a `Shelter` object and a reference to the next node.

---

**Methods:**

- **`__str__()`**  
  Returns a string representation of the linked list of shelters.

- **`is_empty()`**  
  Checks if the linked list is empty.

- **`__getitem__(index)`**  
  Allows accessing shelters by index in the list.

- **`__len__()`**  
  Returns the total number of shelters in the linked list.

- **`occupancy_rate(sector=None)`**  
  Calculates the overall occupancy rate of the shelters in the list. If a sector is provided, it calculates the occupancy rate for shelters serving that sector.

- **`sector_index(sector)`**  
  Returns the index of the first shelter serving the specified sector.

---

**How to Use the Program:**

1. **Reading Shelter Data:**
   The shelter data is stored in a CSV file. The program reads this file and converts the data into `Shelter` objects.

   Example of a CSV file format:
   ```
   ORGANIZATION_NAME,SECTOR,OCCUPIED_BEDS,UNOCCUPIED_BEDS
   Christie Ossington Neighbourhood Centre,Mixed Adult,6,16
   City of Toronto,Mixed Adult,21,27
   Covenant House Toronto,Youth,1,1
   ```

2. **Creating a Linked List:**
   After reading the shelter data from the CSV file, a linked list is created using the `LinkedList` class, which stores the shelter data.

3. **Performing Operations:**
   - To calculate the overall occupancy rate of all shelters:
     ```python
     linked_list.occupancy_rate()
     ```
   - To calculate the occupancy rate of shelters serving "Women":
     ```python
     linked_list.occupancy_rate('Women')
     ```
   - To find the index of the first shelter serving the "Youth" sector:
     ```python
     linked_list.sector_index('Youth')
     ```

---

**Example Usage:**

```python
# Read shelter data from CSV
shelters = read_shelter_data("shelters.csv")

# Create linked list of shelters
linked_list = LinkedList(shelters)

# Calculate overall occupancy rate
print(linked_list.occupancy_rate())  # Output: 98.89

# Calculate occupancy rate for Women shelters
print(linked_list.occupancy_rate('Women'))  # Output: 99.59

# Find the index of the first shelter serving "Youth" sector
print(linked_list.sector_index('Youth'))  # Output: 2
```

---

**Installation Instructions:**

1. Clone the repository.
2. Ensure you have Python 3.x installed.
3. Place the `shelters.csv` file in the same directory as `lab6.py`.
4. Run the script to see the results.

---

**CSV File Format:**

The CSV file should have the following structure:
```
ORGANIZATION_NAME,SECTOR,OCCUPIED_BEDS,UNOCCUPIED_BEDS
Christie Ossington Neighbourhood Centre,Mixed Adult,6,16
City of Toronto,Mixed Adult,21,27
Covenant House Toronto,Youth,1,1
...
```

---

**Requirements:**

- Python 3.x
- No external libraries required

---

**License:**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
