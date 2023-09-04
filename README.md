# [FAQ] GUGC Bioinformatics -   Problem Set 1: Algorithms and complexity

Informatics serves as a foundational prerequisite for this bioinformatics course. As such, we operate under the assumption that you possess a fundamental understanding of Python programming and Unix operating systems. Should you encounter difficulties in grasping the concepts introduced in this course, we strongly urge you to revisit essential topics. These include `file system relative/absolute paths`, `list/dictionary comprehensions` in Python, the use of `positional/keyword arguments` in function calls, as well as `object-oriented programming concepts` like `classes`.

## !!!Notice!!!
[Ufora, shared K-mers] Please put your O(N+M) and O(N*M) solution codes into your answer sheet of Ufora question    

## Q1. How to install `BioPython` on my PyCharm

Please refer to the following: [PyCharm instructions](https://www.jetbrains.com/help/pycharm/installing-uninstalling-and-upgrading-packages.html#interpreter-settings)




## Q2. What happens in `pattern_count(*SeqIO.parse('data.fna', 'fasta'))`? 


First `SeqIO.parse` will read the file 'data.fna' and returns `SeqRecord` iterator. Let us assume that the iterator is a weird tuple. This iterator can be used as passing positional arguments of the function. In the case of pattern_count, the returned two sequence records from `data.fna` will be passed to the first (`string`) and second (`pattern`) parameters of the function pattern_count. You can check this by submitting the following example code to the Dodona system. 

```

def pattern_count(string, pattern):

	print("+++ This is the simple testing using print function +++")

	print("==== what is in the string ====")
	print(string)
	print("==== what type the string is ====")
	print(type(string))

	print("==== what is in the pattern ====")
	print(pattern)
	print("==== what type the pattern is ====")
	print(type(pattern))


	print("==== The SeqRecord has an attribute sequence which contains 'ATCG...' ====")
	print(string.seq)
	print("==== The type of sequence is Seqio.seq ====")
	print(type(string.seq))

	print("==== You can cast the sequence to str ====")
	print(str(string.seq))
	print("==== The type of str(string.seq) is str ====")
	print(type(str(string.seq)))

	return 0
```
For more information, please find the positional/keyword arguments in the informatics lecture (functions) note or the following [Hyperlink](https://problemsolvingwithpython.com/07-Functions-and-Modules/07.07-Positional-and-Keyword-Arguments/)


## Q3. My code cannot read the file on `pattern_count(*SeqIO.parse('data.fna', 'fasta'))`

Your file `data.fna` should be located in the same directory of your python code file. Or you can apply the path. For example, you can specify the absolute path of the file. 
```
pattern_count(*SeqIO.parse('C:\projects\Bioinformatics\problemset1\pattern_count\data.fna', 'fasta'))
```
For more information, please find the `relative/absolute path` in the Google or Informatics lecture notes (Unix parts)


## Q4. Python Tutor is not working. 

`Biopython` is an external package of Python. Therefore The Python tutor in Dodona is no longer available to check the code using `Biopython`. I recommend you use the `print` function to check the variables' values.


## Q5. Whose code is evaluated in the same Group?

We will evaluate the last submission with correct answers. There is no need for two people to post the same code simultaneously, and there is no need for only one person to upload the code. Please study/submit freely and only pay attention to the last submission of each questions.


## Q6. Is multiplication a single operation or multiple additions?

Multiplication is typically implemented as multiple additions at a fundamental level. For basic numeric types like integers and floating-point numbers, both the addition and multiplication operations are generally considered to have constant time complexity $O(1)$. This is because the storage bits for these types are usually fixed at 64-bit or 32-bit.

For instance, the time complexity of multiplication is $O(N \times M)$ when the bit lengths of the numbers to be multiplied are $N$ and $M$ respectively. However, as $N$ and $M$ are usually fixed at 32 or 64, the actual time complexity converges to  $O(1024)$ or $ O(4096) $, which we treat as equivalent to $O(1)$.

For most computational problems, it is safe to assume that multiplication operates in constant time.

*Note: Python has a more sophisticated system for its integers, allowing them to dynamically increase their storage bits. While this may affect time complexity, it is generally considered a special case and is not accounted for in standard time complexity calculations.*

---

## Q7. Is len() a single operation or does it count elements one by one?

In Python, the `len()` function has a time complexity of $O(1)$ for built-in data types like lists, tuples, strings, dictionaries, and sets. This is because these data structures store their length as an attribute, allowing for constant-time retrieval.

*Note: If you define your own data types using classes, the time complexity of the `__len__` method will depend on how you've implemented the code.*
