# Sai Nikhil Vaidyapu
#### New york 

New York City comprises 5 boroughs sitting where the **Hudson River** meets the **Atlantic Ocean**. At its core is Manhattan, a densely populated borough that’s among the world’s major commercial, financial and cultural centers. Its iconic sites include **skyscrapers** such as the Empire State Building and sprawling Central Park.

---
## Maryville to Los Angeles
    1. Directions for Los Angeles
        1. Maryville to Tennessee.
        2. Tennessee to Memphis.
        3. Memphis to Arkansas.
        4. Arkansas to New Mexico.
        5. New Mexico Ferry to Arizona.
        6. Arizona to Los Angeles.
---

### Products to be packed for enjoyment.
* Comfortable Shoes.
* Weather Appropriate, Layered Attire.
* Light Jacket.
* Purse/Backpack.
    * Camera.
    * Extra Batteries/Charger.
    * Refillable Water Bottle.
* Extra Cash.

**[To know more about me](AboutMe.md)**

---

This table shows location and Amount of Foods.

| *Food*                | *Location*      | *Amount*         |
| --------------------- | ----------------| -----------------|
| Biryani               | Suryapet        | 200 INR          |
| Macher Jhol           | Kolkata         | 250 INR          |
| Vada pav              | Mumbai          | 100 INR          |
| Ghevar                | Rajastan        | 150 INR          |

---

# Quotes

>HEATHER FINN Content Strategy Editor
Heather Finn is the content strategy editor at Good Housekeeping, where she heads up the brand's social media strategy and covers entertainment news on everything from ABC's 'The Good Doctor' to Netflix's latest true crime documentaries.
>CAROLINE PICARD Health Editor
Caroline is the Health Editor at GoodHousekeeping.com covering nutrition, fitness, wellness, and other lifestyle news.

---

# Dynamic Programming, Linear Algebra, Numerical Methods

>Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics.
[Dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming)

int n, m;  
vector < vector<long long> > dp;  


void calc (int x = 0, int y = 0, int mask = 0, int next_mask = 0)  
{  
  if (x == n)  
  return;  
  if (y >= m)  
  dp[x+1][next_mask] += dp[x][mask];  
  else  
  {  
        int my_mask = 1 << y;  
        if (mask & my_mask)  
        calc (x, y+1, mask, next_mask);  
        else  

  {
    calc (x, y+1, mask, next_mask | my_mask);  
    if (y+1 < m && ! (mask & my_mask) && ! (mask & (my_mask << 1)))  
    calc (x, y+2, mask, next_mask);  
  }
  }
  }


  int main()  
  {  
  cin >> n >> m;  

  dp.resize (n+1, vector<long long> (1<<m));  
  dp[0][0] = 1;  
  for (int x=0; x<n; ++x)  
  for (int mask=0; mask<(1<<m); ++mask)  
  calc (x, 0, mask, 0);  

  cout << dp[n][0];  
  }

  [Dynamic programming source code](https://cp-algorithms.com/dynamic_programming/profile-dynamics.html)


>Linear algebra is central to almost all areas of mathematics. For instance, linear algebra is fundamental in modern presentations of geometry, including for defining basic objects such as lines, planes and rotations. Also, functional analysis, a branch of mathematical analysis, may be viewed as the application of linear algebra to spaces of functions.

[Linear algebra](https://en.wikipedia.org/wiki/Linear_algebra)

const double EPS = 1e-9;
const int INF = 2; // it doesn't actually have to be infinity or a big number

  int gauss (vector < vector<double> > a, vector<double> & ans)  
  {  
  int n = (int) a.size();  
  int m = (int) a[0].size() - 1;  

  vector<int> where (m, -1);  
  for (int col=0, row=0; col<m && row<n; ++col)  
  {  
  int sel = row;  
  for (int i=row; i<n; ++i)  
  if (abs (a[i][col]) > abs (a[sel][col]))  
  sel = i;  
  if (abs (a[sel][col]) < EPS)  
  continue;  
  for (int i=col; i<=m; ++i)  
  swap (a[sel][i], a[row][i]);  
  where[col] = row;  

  for (int i=0; i<n; ++i)  
  if (i != row)  
  {  
  double c = a[i][col] / a[row][col];  
  for (int j=col; j<=m; ++j)  
  a[i][j] -= a[row][j] * c;  
  }  
  ++row;  
  }

  ans.assign (m, 0);  
  for (int i=0; i<m; ++i)  
  if (where[i] != -1)  
  ans[i] = a[where[i]][m] / a[where[i]][i];  
  for (int i=0; i<n; ++i)
  {  
  double sum = 0;  
  for (int j=0; j<m; ++j)  
  sum += ans[j] * a[i][j];  
  if (abs (sum - a[i][m]) > EPS)  
  return 0;  
  }  

  for (int i=0; i<m; ++i)  
  if (where[i] == -1)  
  return INF;  
  return 1;  
  }

  [Linear algebra source code](https://cp-algorithms.com/linear_algebra/linear-system-gauss.html)

>In numerical analysis, a numerical method is a mathematical tool designed to solve numerical problems. The implementation of a numerical method with an appropriate convergence check in a programming language is called a numerical algorithm.

[Numerical method](https://en.wikipedia.org/wiki/Numerical_method)

  double ternary_search(double l, double r)   
  {  
  double eps = 1e-9;  
  //set the error limit here  
  while (r - l > eps)  
  {  
  double m1 = l + (r - l) / 3;  
  double m2 = r - (r - l) / 3;  
  double f1 = f(m1);  
  //evaluates the function at m1  
  double f2 = f(m2);  
  //evaluates the function at m2  
  if (f1 < f2)  
  l = m1;  
  else  
  r = m2;  
  }  
  return f(l);  
  //return the maximum of f(x) in [l, r]  
  }

  [Numerical method source code](https://cp-algorithms.com/num_methods/ternary_search.html)




