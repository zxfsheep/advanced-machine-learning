* [**"SVD"**](http://sifter.org/~simon/journal/20061211.html): Low rank matrix factorization. Not really SVD in linear algebra.
* [**"SVD"++**](https://github.com/gpfvic/IRR/blob/master/Factorization%20meets%20the%20neighborhood-%20a%20multifaceted%20collaborative%20filtering%20model.pdf): A user is not only represented by its vector, but also the bag of vectors corresponding to the user's items.
* [**Factorization Machine**](https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf): Each feature column is embedded as a vector $v_i$ in some fixed dimensional space, and the interaction between columns are modeled by $<v_i, v_j>$. These are defined independently of sample values. If a sample has $x_i, x_j$ at those columns, the contribution to the target (label, regression,...) is $x_ix_j<v_i, v_j>$. When we just have two categorical variables, users and items, each row is a pair of user and item, one-hot encoded, then this is equivalent to matrix factorization. But FM is much more general.
* **Field-aware Factorization Machine**:
* **Restricted Boltzmann Machine**:

