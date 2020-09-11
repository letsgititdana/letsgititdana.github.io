# R Basics Review

*R* is a *language* and environment for statistical computing and graphics.

[Visit the official website (r-project.org) for more information about R](https://www.r-project.org/about.html)



## 1. Basic Data Types and Sets in R

![image-20200911193826887](/Users/Dana/Library/Application Support/typora-user-images/image-20200911193826887.png)

* **R's** basic data **types** are character, numeric, complex, and logical.

  * character: `"a"`, "`abc`"
  * numeric: `1`, `123` (`1L` to store an integer)
  * complex: `1+2i` (complex with imaginary numbers)
  * logical: `TRUE`, `FALSE`

  

  **How to check data types in R:**

  ```R
  is.character("abc")  # returns TRUE
  is.integer(3.5)			 # returns FALSE
  
  class("abc")				 # returns "character" (high-level type)
  typeof("abc")				 # returns "character" (low-level type)
  ```

  These are also possible: is.null(x), is.na(x), is.nan(x), is.finite(x), is.infinite(x)

  

  **How to change data types in R:**

  ```R
  as.character(3.5)		# returns "3.5" (character)
  as.integer("3.5")		# returns 3.5 (integer)
  ```

  

* **R's** basic **data structures** include vector, factor, matrix, array, list, and data frame.

  * **Vector**: a basic data structure in R. Vectors are the simplest form of objects in R. It contains element of the same type. The data types can be logical, integer, double, character, complex or raw.

    * Requires all members to be of the same data type.
    * functions: c(), seq(), rep(), length(), names(), sort(), order() ...
    * indexing: [i]

    

  * **Factor**: vector used for fields that takes only predefined, finite number of values (categorical data) called *levels*.

    * Requires all members to be of the same data type.
    * functions: factor(vector[, levels=  ]), levels()
    * indexing: [i]

    

  * **Matrix**: two dimensional vector. Matrix is similar to vector but additionally contains the dimension attribute.

    * Requires all members to be of the same data type.
    * functions: matrix(vector, nrow=  ,ncol=  ), rbind(), cbind(), dim(), colnames(), rownames(), rowSums(), colSums(), rowMenas(), colMeans()
    * indexing: [row, col]

  

  * **Array**: more than two dimensional vector.  
    * Requires all members to be of the same data type.
    * functions: array()
    * indexing: [row, col, dim]

  

  * **List**: a data structure having components of mixed data types. A vector having elements of different type is called list.
    * Members can have different data types.
    * functions: list(), unlist()
    * indexing: [ ], [[ ]], $

  ![image-20200911200541093](/Users/Dana/Library/Application Support/typora-user-images/image-20200911200541093.png)

  

  * Data Frame: two dimensional data structure. It is a special case of a list which has each component of equal length. Each component form the column and contents of the component form the rows.

    * Members can have different data types.
    * functions: data.frame(), as.data.frame(), rbind, bind, str(), subset()
    * indexing: [row, col], dataframe$colname, [[row]]

    

![download](/Users/Dana/Desktop/download.png)



## 2. Basic R Operators

* **{ }**

* **( )**

* **$**

* **[ ], [[ ]]**

* **^, ****

* **-**

* **:**

* **%*%, %/%, %%**

* **+, -, *, /**

* **<, >, <=, >=, ==**

* **!**

* **&, &&, |, ||**

* **<-, =**

  > The operators `<-` and `=` assign into the environment in which they are evaluated. The operator `<-` can be used anywhere, whereas the operator `=` is only allowed at the top level (e.g., in the complete expression typed at the command prompt) or as one of the subexpressions in a braced list of expressions.

* **<<-** 

  > The operators `<<-` and `->>` are normally only used in functions, and cause a search to be made through parent environments for an existing definition of the variable being assigned. If such a variable is found (and its binding is not locked) then its value is redefined, otherwise assignment takes place in the global environment. 