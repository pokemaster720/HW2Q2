# HW2Q2

### Libraries Used
- `collections.Counter`
- `math`
- `calculate_information_gain`
  
### Data Description - Classification
- `Training_data`:  inner list represents an instance (or record) and consists of categorical attributes (Education, Career, Years of Experience).
- `labels`:  in `Training_data` ("Low" or "High" salary).
- `features`: Identifiers for the categories of features in `Training_data`.
- `validation_data` and `validation_labels`: lists intended for pruning the decision tree using validation data.

### Functions Explained
1. **`calculate_entropy(labels) -> float`:
   - **Purpose**: Calculate the entropy of a list of classification labels.
        - Entropy measures the randomness in the set, which is crucial for deciding on splits in a decision tree.
   - **Parameters: `labels`
        - list of classification labels.
   - **Process: 
        -  `Counter` to count occurrences of class labels, calculates their probabilities, and computes entropy according to
        -   the formula \(Entropy = -\sum (p \times \log_2(p))\).
   - **Returns: The calculated entropy as a float.

2. **Conditional Statement involving `low_salary_count + high_salary_count`:
   - used intended to calculate the total entropy for salary data (either "High" or "Low" salaries) by using the `calculate_entropy` function.

3. **`divide_entropy(subsets) -> float`:
   - **Purpose**: Calculate the weighted average of entropy for a given division of data subsets.
         - its useful in the decision of tree algorithms to measure the effectiveness of a split.
   - **Process**:
         - the entropy for each subset by weighing the subset's proportion to the total number of instances.
     
   - **Returns**: The weighted average entropy.


4. **DecisionTreeNode Class:
      - Each node can either be a decision node - feature_index and a feature_value 
          - or a leaf node- a predicted class label for that branch.

5. **divide_dataset Function**:
      - Splits the dataset and corresponding labels based on a specified feature index and its value.
      - function is essential for recursively dividing the dataset as the tree grows, ensuring each child node gets the correct subset of data.

6. **build_tree Function**:
       - checks for base cases- the dataset is empty or all instances belong to the same class).
       - It then finds the best feature to split on by calculating the information gain for all features.
       - Next, it creates a new node based on the best feature and recursively builds the tree for each subset of the dataset resulting from splitting on the best feature.

7. Error Handling and Validation
       - Checking if data and labels are lists, and if their lengths match.
       - Ensuring feature index is within the bounds of the dataset.
       - Handling cases where there is an empty dataset or labels/features are missing.

   <img width="1098" alt="Screenshot 2024-03-04 at 12 38 55 AM" src="https://github.com/pokemaster720/HW2Q2/assets/84993132/e7aedd9c-4d0e-4a7e-a26a-1c0a58a27b4c">
