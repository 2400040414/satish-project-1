# satish-project-1# Step 1: Initialize repo and commit initial version
git init myproject
cd myproject

echo "function greet() {
  console.log('Hello from main branch');
}" > App.js

git add App.js
git commit -m "Initial commit with greet function"

# Step 2: Create branch feature1 (Alice's branch)
git checkout -b feature1

# Alice edits App.js
echo "function greet() {
  console.log('Hello from Alice in feature1 branch!');
}" > App.js

git add App.js
git commit -m "Alice modifies greet in feature1"

# Step 3: Create branch feature2 from main (Bob's branch)
git checkout main
git checkout -b feature2

# Bob edits App.js
echo "function greet() {
  console.log('Hello from Bob in feature2 branch!');
}" > App.js

git add App.js
git commit -m "Bob modifies greet in feature2"

# Step 4: Merge feature1 into main (no conflict)
git checkout main
git merge feature1

# Step 5: Merge feature2 into main (conflict happens)
git merge feature2
