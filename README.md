# TV-Series
### **📜 TV Series Database**  
A structured database to manage TV series, actors, episodes, viewers, and viewership data using **Oracle SQL**.

---

## **📌 Project Overview**  
This project is a **TV Series Management Database** designed for a coursework.  
It includes SQL scripts for:  
✅ Creating tables and sequences  
✅ Adding constraints (PK, FK, UNIQUE, CHECK)  
✅ Inserting sample data  
✅ Querying data with complex SQL queries  
✅ Dropping tables and constraints  

---

## **⚙️ Database Structure**  
The database consists of the following tables:  
- **`actors`** – Stores actor details (name, country, email, etc.)  
- **`series`** – Stores TV series information  
- **`casting`** – Maps actors to series and their roles  
- **`episode`** – Stores episodes per series  
- **`viewer`** – Stores viewer details  
- **`viewership`** – Tracks which viewer watched which episode  

---

## **📂 Project Files**  
| File Name                         | Description |
|-----------------------------------|-------------|
| `A. create.txt` | Contains `CREATE TABLE` statements and sequences. |
| `B. constraint.txt` | Defines `PRIMARY KEYS`, `FOREIGN KEYS`, and constraints. |
| `C. insert.txt` | Inserts sample data into tables. |
| `D. drop.txt` | Drops all tables and constraints in order. |
| `E. query.txt` | Various SQL queries for analysis. |

---

## **🚀 Setup Instructions**  
1. **Open SQL Developer / Oracle SQL Plus**  
2. **Run the scripts in order:**  
   ```sql
   @A. create.txt
   @B. constraint.txt
   @C. insert.txt
   ```
3. **Run Queries for Testing:**  
   ```sql
   @E. query.txt
   ```
4. **Drop Tables (if needed):**  
   ```sql
   @D. drop.txt
   ```

---

## **🔍 Sample Queries**  
Example: Fetch all actors from the USA  
```sql
SELECT A_First_Name, A_Surname FROM actors WHERE A_Country = 'USA';
```
Example: Find the most-watched series  
```sql
SELECT series.S_Title, COUNT(viewership.Viewer_id) AS TotalViews
FROM series
JOIN viewership ON series.Series_id = viewership.Series_id
GROUP BY series.S_Title
ORDER BY TotalViews DESC
FETCH FIRST 1 ROW ONLY;
```

---

## **📌 Notes**  
- Uses **Oracle SQL** (ensure Oracle DB compatibility).  
- Date format: `03-Mar-2024`.  
- Text fields are stored in **UPPERCASE**.  
- Ensure **sequences** are set up before inserting data.  

---
