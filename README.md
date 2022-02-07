- 👋 Hi, I’m @pankaj-hash
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
pankaj-hash/pankaj-hash is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Locality Sensitive Hashing

This notebook is a tutorial and python implementation of locality sensitive hashing.

We demonstrate the tools using a very very small dataset, consisting of 4 articles pulled from CNN, and a 5th that is a partial concatenation of 3 of those, to artificialy produce some high similarity scores.

Since this is a small dataset, we can easily compare our approximations to the true similarity scores amongst text files. We do so throughout. The layout of this notebook is as follows:

Part I: computing similarity amongst text documents
1. Introduce a shingle function. Clean and split each text file into a set of K-shingles
2. Compute the exact Jaccard similarity (intersection over union) between all pairs
3. Create and apply a MinHashing class:
    1. Initialize with a dictionary of key-value pairs for the shingles
    2. Apply "universal hashing" to perform minhashing on a shingle set
    3. can be called like a function to compute a **signature matrix**
4. Evaluate MinHashing effectiveness by computing scores of all pairs
5. Introduce LSH for finding **candidate pairs**, i.e. use a banded signature matrix to find all pairs whose similarity is likely above a threshold
6. Make this efficient, by using hash table for band, column ids, allowing O(n) comparison

Part II: computing similarity amongst vectors

* Afterwards, we provide an additional LSH family for Euclidean spaces, namely cosine similarity. 
* This is used to ascertain the similarity of vectors in a D-dimensional space.
* Can be implemented using the *Random Hyperplanes* hashing method.
