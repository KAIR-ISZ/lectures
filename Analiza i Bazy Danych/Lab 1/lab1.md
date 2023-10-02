**Title: Introduction to R Programming**

**Duration:** 90 minutes

**Objective:** To introduce students to the basics of the R programming language and help them build a foundational understanding of key concepts.

**Materials Needed:**
- Computers with R and RStudio installed (if available)
- R installed on your machine (for demonstrations)
- Projector or whiteboard for presentations
- Exercise handouts for students

**Introduction (15 minutes):**
1. **Welcome and Icebreaker (5 minutes):** Start the class with a brief introduction of yourself and ask students to share their names and one thing they hope to learn from this R programming class.

2. **Why Learn R? (5 minutes):** Explain why R is important. Mention its popularity in data analysis, data visualization, and statistical modeling.

3. **What is R? (5 minutes):** Provide a simple definition of R: R is an open-source programming language and environment used for statistical computing and data analysis.

**Basic Concepts (30 minutes):**

4. **RStudio and R Console (10 minutes):** Demonstrate how to open RStudio and the R Console. Explain that RStudio is an integrated development environment (IDE) for R.

5. **Variables and Data Types (10 minutes):** Discuss basic data types in R, including numeric, character, logical, and factors. Show how to assign values to variables and how to check variable data types.

6. **Vectors (10 minutes):** Introduce vectors as the fundamental data structure in R. Explain how to create and manipulate vectors.

**Exercise 1: Creating Vectors (10 minutes):**
Provide students with a list of values and ask them to create a numeric vector to store these values. Then, ask them to perform basic operations like finding the mean and sum of the values.

**Control Structures (20 minutes):**

7. **If Statements (10 minutes):** Explain how to use if statements for conditional execution. Provide examples and show how to structure if-else statements.

8. **Loops (10 minutes):** Introduce for and while loops. Discuss their syntax and use cases.

**Exercise 2: Conditional Statements (10 minutes):**
Provide a problem where students need to use if-else statements to check conditions and perform different actions based on the condition.

**Data Frames (15 minutes):**

9. **Introduction to Data Frames (10 minutes):** Explain what data frames are and why they are essential in R for working with tabular data.

**Exercise 3: Creating and Manipulating Data Frames (15 minutes):**
Give students a small dataset and ask them to create a data frame, add columns, and perform basic operations like filtering and summarizing.

**Data Visualization (10 minutes):**

10. **Introduction to ggplot2 (10 minutes):** Briefly introduce the ggplot2 package for data visualization in R. Show how to create simple plots.

**Exercise 4: Data Visualization (15 minutes):**
Provide a dataset and ask students to create a basic plot using ggplot2, such as a scatterplot or bar chart.

**Conclusion and Next Steps (5 minutes):**
Summarize the key points covered in the class and encourage students to continue exploring R on their own. Mention resources for further learning, such as online tutorials and forums.

**Exercise 5: Homework Assignment (5 minutes):**
Assign a simple R programming task for homework to reinforce the concepts learned in class, such as calculating descriptive statistics or plotting a graph.

**Q&A and Closing (5 minutes):**
Invite students to ask questions and address any concerns they may have. Thank them for attending the session and express your enthusiasm for their journey into R programming.

**Note:** Adjust the duration of each section as needed to fit the time available. The exercises can be modified for different skill levels, and it's essential to provide additional resources for students to continue learning independently.




Certainly! Here are more detailed descriptions of the five exercises, including solutions and example data where necessary:

**Exercise 1: Creating Vectors (10 minutes)**

*Description*: Provide students with a list of values (e.g., 5, 10, 15, 20, 25) and ask them to create a numeric vector to store these values. Then, instruct them to calculate and print the mean and sum of the values in the vector.

*Example Data*: Values to create a vector: `5, 10, 15, 20, 25`

*Solution*:
```R
# Create a numeric vector
my_vector <- c(5, 10, 15, 20, 25)

# Calculate and print the mean
mean_value <- mean(my_vector)
cat("Mean:", mean_value, "\n")

# Calculate and print the sum
sum_value <- sum(my_vector)
cat("Sum:", sum_value, "\n")
```

**Exercise 2: Conditional Statements (10 minutes)**

*Description*: Provide a problem statement like: "You have a list of exam scores. Write R code to check if each score is passing (greater than or equal to 60) or failing (less than 60). Print 'Pass' or 'Fail' accordingly."

*Solution*:
```R
# Example data: List of exam scores
scores <- c(75, 48, 90, 60, 30)

# Loop through the scores and check if each is passing or failing
for (score in scores) {
  if (score >= 60) {
    cat("Pass\n")
  } else {
    cat("Fail\n")
  }
}
```

**Exercise 3: Creating and Manipulating Data Frames (15 minutes)**

*Description*: Provide a small dataset like the following:

```
Name, Age, Score
Alice, 25, 85
Bob, 30, 92
Carol, 28, 78
```

Ask students to create a data frame from this data and then perform the following tasks:
- Add a new column "Grade" based on a condition (e.g., A for scores >= 90, B for scores >= 80, and C for scores < 80).
- Filter the data frame to show only the rows where Age is less than 30.

*Solution*:
```R
# Example data
data <- data.frame(
  Name = c("Alice", "Bob", "Carol"),
  Age = c(25, 30, 28),
  Score = c(85, 92, 78)
)

# Add a new column "Grade" based on conditions
data$Grade <- ifelse(data$Score >= 90, "A",
                     ifelse(data$Score >= 80, "B", "C"))

# Filter the data frame to show only rows where Age is less than 30
filtered_data <- data[data$Age < 30, ]

# Print the modified data frame
print(filtered_data)
```

**Exercise 4: Data Visualization (15 minutes)**

*Description*: Provide a dataset of students and their test scores. Ask students to create a bar chart using ggplot2 to visualize the average scores for different subjects. The dataset could look like this:

```
Subject, Average_Score
Math, 85
Science, 92
History, 78
```

*Solution*:
```R
# Example data
data <- data.frame(
  Subject = c("Math", "Science", "History"),
  Average_Score = c(85, 92, 78)
)

# Load the ggplot2 library
library(ggplot2)

# Create a bar chart
ggplot(data, aes(x = Subject, y = Average_Score, fill = Subject)) +
  geom_bar(stat = "identity") +
  labs(title = "Average Scores by Subject",
       x = "Subject",
       y = "Average Score") +
  theme_minimal()
```

**Exercise 5: Homework Assignment (5 minutes)**

*Description*: Assign a homework task for students to calculate descriptive statistics for a given dataset. Provide a dataset (e.g., a list of exam scores) and ask students to write R code to calculate the mean, median, and standard deviation of the data.

*Example Data*: Exam scores: `75, 48, 90, 60, 30`

*Solution*:
```R
# Example data
exam_scores <- c(75, 48, 90, 60, 30)

# Calculate mean, median, and standard deviation
mean_value <- mean(exam_scores)
median_value <- median(exam_scores)
sd_value <- sd(exam_scores)

# Print the results
cat("Mean:", mean_value, "\n")
cat("Median:", median_value, "\n")
cat("Standard Deviation:", sd_value, "\n")
```

These exercises cover fundamental concepts in R, including data manipulation, control structures, data frames, and data visualization. Students should be able to gain confidence in using R for basic data analysis after completing these exercises.
