
**Lesson 4 Homework: Command Line Chipotle**
This folder contains solutions for class 4 homework. Answers are listed under the questionx
1. Command Line Tasks
    Look at the head and the tail of chipotle.tsv in the data subdirectory of this repo. Think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)
    <br>
    `head chipotle.tsv`
    <br>
    `Tail chipotle.tsv`
    <br>
    It is a tab seperated file with each row re-presenting items purchased. Multiple items within same order are listed as seperate rows. Order ID is linking them together. Each column provides more details about the item purchased
    </br>
    
2. How many orders do there appear to be?
    <br>
    Approach: Cut the file with only order id as column, sort by that column, perform a uniq operation. count the lines.
    <br>
    Code:
    <br>
    `cut -f1 chipotle.tsv > chipotle_OrderColumn.tsv
    sort chipotle_OrderColumn.tsv > chipotle_Sorted_OrderColumn.tsv
    uniq chipotle_Sorted_OrderColumn.tsv > chipotle_uniq_sorted_order_column.tsv
    wc -l chipotle_uniq_sorted_order_column.tsv`
    <br>
    Answer:
    There are **1834** unique orders in the file. The above operation could also be performed by using | to feed output of first command into the next command. I created filed here for clarity purposes.
    <br>
3. How many lines are in this file?
  <br>
  `wc -l chipotle.tsv`
  <br>
  There are **4622** lines in the file
  <br>
4. Which burrito is more popular, steak or chicken?
  <br>
  `grep -c 'Chicken Burrito' chipotle.tsv
   grep -c 'Steak Burrito' chipotle.tsv
   `
   553 chipotle_ChickenBurrito.tsv
   368 chipotle_SteakBurrito.tsv
    Answer: Chicken is more popular than steak
  <br>
5. Do chicken burritos more often have black beans or pinto beans?
  <br>
  `grep 'Chicken Burrito' chipotle.tsv | grep -c 'Black Beans'
   grep 'Chicken Burrito' chipotle.tsv | grep -c 'Pinto Beans'`
  282
  105
  Answer:Chicken Burritos have black beans more often than pinto beans
  <br>
6. Make a list of all of the CSV or TSV files in the [our class repo] (https://github.com/ga-students/DS-SEA-07). repo (using a single command). You will be working on your local repo on your laptop. Think about how wildcard characters can help you with this task.
  <br>
  `find . -name *.csv -or -name *.tsv`
  <br>
7. Count the approximate number of occurrences of the word "dictionary" (regardless of case) across all files of [our class repo] (https://github.com/ga-students/DS-SEA-7).
  <br>
  `grep -i -o 'dictionary' -r . | wc -l`
  Answer: There are 56 occurance
  <br>
8. Optional: Use the the command line to discover something "interesting" about the Chipotle data. Try using the commands from the "advanced" section!
  <br>
  ``
  <br>
