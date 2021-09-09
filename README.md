- 👋 Hi, I’m @Vkvarmach
- 👀 I’m interested in programming
- 🌱 I’m currently learning devoloping web appications...
- 💞️ I’m looking to collaborate on google
- 📫 How to reach me chunchuvijaykumar96@gmail.com...

<!---
Vkvarmach/Vkvarmach is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Chunchu_Assignment2
# VIJAY KUMAR CHUNCHU
###### DELHI
>Delhi is the **capital city** of India. It is well known **tourist place** to visit and also we can find a lot of different culutural tradition.Delhi has many **historical places** to visit.

************************************************

###### Direction using orderd list

1. Maryville
2. kansas
    1. kansas airport
    2. boarding terminal
    3. aeroplane
3. delhi

### items using unordered list

* camera
    * best images
* Bike
* Food
    * Biryani

    **[LinktoAboutMe.md](AboutMe.md)**

    ---------------

    ## Table of food items
>To create a table with at least 4food/drinksthat I would recommend someone try.Include a short paragraph that introduces the table.

|mandatory     |fav1     |fav2     |fav3     |fav4     |
| :-----:      | :-----: | :-----: | :-----: | :-----: |
|food/drink    |biryani  |pasta    |pizza    |pepsi    |
|location      |hyderabad|delhi    |vizag    |mumbai   |
|money         |50-40    |40-30    |30-20    |20-10    |

 --------------

 ## Quotes section
>"Varmas kings by blood".
Author: *shivaji* <br>
>"Think about your thinking".
Author: *balakrishna* <br>

**********************

### Code fencing
>Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics. quick source code <https://en.wikipedia.org/wiki/Dynamic_programming>

int m, n;
vector<long long> dp_before(n), dp_cur(n);

long long C(int i, int j);

// compute dp_cur[l], ... dp_cur[r] (inclusive)
void compute(int l, int r, int optl, int optr) {
    if (l > r)
        return;

    int mid = (l + r) >> 1;
    pair<long long, int> best = {LLONG_MAX, -1};

    for (int k = optl; k <= min(mid, optr); k++) {
        best = min(best, {(k ? dp_before[k - 1] : 0) + C(k, mid), k});
    }

    dp_cur[mid] = best.first;
    int opt = best.second;

    compute(l, mid - 1, optl, opt);
    compute(mid + 1, r, opt, optr);
}

int solve() {
    for (int i = 0; i < n; i++)
        dp_before[i] = C(0, i);

    for (int i = 1; i < m; i++) {
        compute(0, n - 1, 0, n - 1);
        dp_before = dp_cur;
    }

    return dp_before[n - 1];
}

quick source code <https://cp-algorithms.com/dynamic_programming/divide-and-conquer-dp.html>
