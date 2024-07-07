To accomplish the project tasks using Nano commands and shell scripting (.sh file), you can follow these steps:

### Step-by-Step Instructions

1. **Create two directories under the root folder:**

   ```bash
   mkdir directory1 directory2
   ```

2. **Create ten documents in each directory:**

   ```bash
   for ((i=1; i<=10; i++)); do touch directory1/doc$i.txt; done
   for ((i=1; i<=10; i++)); do touch directory2/doc$i.txt; done
   ```

3. **Add content to all documents:**

   For simplicity, let's add some text to each document using `echo`:

   ```bash
   for file in directory1/*.txt; do echo "Initial content" > "$file"; done
   for file in directory2/*.txt; do echo "Initial content" > "$file"; done
   ```

4. **Update all documents by appending five lines of phrase to each document:**

   Here, we'll use a loop to append five lines to each file:

   ```bash
   for file in directory1/*.txt; do
       for ((i=1; i<=5; i++)); do
           echo "Additional line $i" >> "$file"
       done
   done

   for file in directory2/*.txt; do
       for ((i=1; i<=5; i++)); do
           echo "Additional line $i" >> "$file"
       done
   done
   ```

5. **Delete one document from each directory:**

   You can delete one document from each directory, for example:

   ```bash
   rm directory1/doc1.txt
   rm directory2/doc1.txt
   ```

6. **Create a shell script (.sh file) to automate the above steps:**

   Create a file named `project_tasks.sh`:

   ```bash
   nano project_tasks.sh
   ```

   Add the following content to `project_tasks.sh`:

   ```bash
   #!/bin/bash

   # Step 1: Create directories
   mkdir directory1 directory2

   # Step 2: Create 10 documents in each directory
   for ((i=1; i<=10; i++)); do touch directory1/doc$i.txt; done
   for ((i=1; i<=10; i++)); do touch directory2/doc$i.txt; done

   # Step 3: Add initial content
   for file in directory1/*.txt; do echo "Initial content" > "$file"; done
   for file in directory2/*.txt; do echo "Initial content" > "$file"; done

   # Step 4: Append five lines to each document
   for file in directory1/*.txt; do
       for ((i=1; i<=5; i++)); do
           echo "Additional line $i" >> "$file"
       done
   done

   for file in directory2/*.txt; do
       for ((i=1; i<=5; i++)); do
           echo "Additional line $i" >> "$file"
       done
   done

   # Step 5: Delete one document from each directory
   rm directory1/doc1.txt
   rm directory2/doc1.txt

   echo "Project tasks completed."
   ```

   Save and close the file (`Ctrl+X`, `Y`, `Enter`).

7. **Make the script executable:**

   ```bash
   chmod +x project_tasks.sh
   ```

8. **Run the script:**

   ```bash
   ./project_tasks.sh
   ```

### Explanation

- **`mkdir`**: Creates directories named `directory1` and `directory2`.
- **`touch`**: Creates empty files (`doc1.txt` to `doc10.txt`) in each directory.
- **`echo "Initial content" > "$file"`**: Adds initial content to each file.
- **Appending lines**: Uses nested loops to append five lines of text to each document.
- **`rm`**: Deletes `doc1.txt` from each directory.
- **Shell script**: Combines all these commands into a reusable script (`project_tasks.sh`).

This script will automate the entire process as per your project requirements using shell commands and a shell script file. Adjust paths and specific commands as needed for your environment and exact file structure.
