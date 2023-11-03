<p align="center">
  <a href="https://github.com/RAJCHAKRABORTY3416/CN-world-cup">
    <img src="https://www.financialexpress.com/wp-content/uploads/2023/05/APIS-and-NxtWave-image-37-3.jpg" alt="Logo" width="400" height="170">
  </a>
</p>

### Problem Number 1

```cpp
int minDifference (vector<int> &a) {
    sort(a.begin(), a.end()); 
    int diff=INT_MAX;
    for (int i=1;i<a.size();i++){ 
        if (a[i]-a[i-1]<diff){ 
            diff=a[i]-a[i-1];
        }
    }
return diff;
}
```

### Problem Number 2

```cpp
int coinGame(int x, int y) {
    int s;
    if(x>=y*3){
        s=y;
    }
    else{
        s=x/3;
    }
    return s%2;
}
```

### Problem Number 4

```cpp
int liftStruggle (int d) { 
    int sum=d/3;
    if (d-(sum*3)==0) {
        return sum;
    }
    else if (d-(sum*3)==1){
        return sum+2;
    }
    else {
        return sum+4;
    }
}
```

### Problem Number 5

```cpp
int goodSubsequence(vector<int> &a) {
    int mod = 1e9 + 7;
    long long ans = 1;
    unordered_map<int, int> m;
    for (int i = 0; i < a.size(); i++) {
        m[a[i]]++;
    }
    for (auto it : m) {
        ans = (ans % mod * (it.second + 1) % mod);
    }
    ans = (ans - 1 + mod) % mod;
    return ans;
}
```

### Problem Number 7

```cpp
int nines(int n, vector<int> &a, int k) {
  int count = 0;
  for (int i = 0; i < n; i++) {
    if (a[i] == 9) {
      count++;
    }
  }
  if (count >= k) {
    return 1;
  } else {
    return 0;
  }
}

```

### Problem Number 8

```cpp
vector<long long> countOperations(int N, vector<int> &A, long long X, int q, vector<vector<int>> &queries) {
    // Write your code here.
    vector<long long> result;

        long long sumA = 0;
            
                for (int i = 0; i < N; i++) {
                        sumA += A[i];
                            }

                                for (int i = 0; i < q; i++) {
                                        int K = queries[i][0];
                                                int Y = queries[i][1];
                                                        sumA = sumA - A[K] + Y;
                                                                A[K] = Y;

                                                                        long long operations = (sumA + X - 1) / X;
                                                                                result.push_back(operations);
                                                                                    }

                                                                                        return result;
}
```

### Problem Number 10

```cpp
long long totalChocolates(int n, vector<int> a) { 
    long long placementlelo = 0; 
    for(int i=0; i<n; i++){ 
        if(a[i]>23){ 
            placementlelo+= a[i]-23; 
        } 
    } 
    return placementlelo; 
} 
```

### Problem Number 11

```cpp
long long cyclicBeauty(int n, vector<int> &a) {
    // Write your code here.
     long long totalProficiency = 0;
        long long maxProficiency = 0;

            for (int i = 1; i < n; i++) {
                    totalProficiency += abs(a[i] - a[i - 1]);
                        }

                            for (int i = 0; i < n; i++) {
             maxProficiency = max(maxProficiency, totalProficiency);
            totalProficiency += abs(a[i] - a[(i + n - 1) % n]) - abs(a[(i + 1) % n] - a[i]);
                                                }
                                                return maxProficiency;
}
```

### Problem Number 13

```cpp
#include <bits/stdc++.h> 
long long countPairs(int n, vector<int> a) { 
     
    int maxi = *max_element(a.begin(), a.end()); 
    int mini = *min_element(a.begin(), a.end()); 
    int cmini = 0; 
    int cmaxi = 0; 
 
    sort(a.begin(), a.end()); 
    if(a[0] == a[n-1])return n*(n-1); 
 
    for(int i = 0; i<n; i++){ 
        if(a[i] == mini){ 
            cmini++; 
        } 
        if(a[i]== maxi){ 
            cmaxi++; 
        } 
    } 
 
    return cmini*cmaxi*2; 
} 
```

### Problem Number 14

```cpp
int kaiserImpact(int n, int m, int a, int b, int w, double k) {
    // Write your code here.
     if(k==0){ 
      return 0; 
  } 
 double maxY = k * a; 
         
 if (maxY > m || maxY - w >= b) {                       
            return 0; 
              } 
                    return 1;     
}

```

### Problem Number 16

```cpp
int planetMisery(int n, int m){ 
    if(abs(n-m)>1){ 
        return ((max(n,m)-abs(n-m))*2)+1; 
    } 
    return n+m; 
}
```

### Problem Number 17

```cpp
int xorScore(int a,int b) {
    // Write your code here.
      return ((a+b)>(a^b))?1:0;
}
```

### Problem Number 19

```cpp
int replaceElements(vector<int> &a){ 
    int placementlelo = a.size(); 
    if(placementlelo%2==1){ 
        return -1; 
    } 
    int maxi = *max_element(a.begin(),a.end()); 
    vector<int>hash(max(maxi+1,placementlelo),0); 
    for(int i=0; i<placementlelo; i++){ 
        hash[a[i]]++; 
    } 
    int c = 0; 
    for(int i=0; i<=max(maxi+1,placementlelo); i++){ 
        if(hash[i]%2==1)c++; 
    } 
    return c/2; 
}

```

### Problem Number 20

```cpp
#include <bits/stdc++.h>
using namespace std;

bool isPrime(int num){
    if (num <= 1) {
        return false;
    }
    int srt = sqrt(num);
    for (int i = 2; i <= srt; i++){
        if (num % i == 0) return false;
    }
    return true;
}

int helper(vector<int>& a, int n, int m, int sum) {
    if (m == 0) return isPrime(sum) ? 1 : 0;
    if (n == 0) return 0;

    return helper(a, n - 1, m - 1, sum + a[n - 1]) + helper(a, n - 1, m, sum);
}

int primeSum(int n, int m, vector<int>& a) {
    return helper(a, n, m, 0);
}
```

### Problem Number 22

```cpp
long long bestWorkers(int n, int k, std::vector<int> &a) {
    long long maxSum = 0;
    long long currentSum = 0;

    for (int i = 0; i < k; i++) {
        currentSum += a[i];
    }

    maxSum = currentSum;

    for (int i = k; i < n; i++) {
        currentSum += a[i] - a[i - k];
        maxSum = std::max(maxSum, currentSum);
    }

    return maxSum;
}

```

### Problem Number 23

```cpp
#include <vector>
#include <algorithm>

using namespace std;

bool isPossible(const vector<int> &a, int m, long long maxOR) {
    long long curOR = 0;
    int groups = 0;

    for (int i = 0; i < a.size(); ++i) {
        curOR |= a[i];

        if (curOR > maxOR) {
            curOR = a[i];
            groups++;

            if (groups >= m)
                return false;
        }
    }

    return true;
}

long long optimalDivision(int m, vector<int> &a) {
    long long left = 0;
    long long right = 0;

    for (int i = 0; i < a.size(); ++i) {
        left = max(left, (long long)a[i]);
        right += a[i];
    }

    while (left < right) {
        long long mid = left + (right - left) / 2;

        if (isPossible(a, m, mid)) {
            right = mid;
        } else {
            left = mid + 1;
        }
    }

    return left;
}

```

### Problem Number 25

```cpp
int boxFilling(int n, int x, int y){ 
    return (n*x)%y==0?(n*x)/y:(n*x)/y+1; 
}
```

### Problem Number 26

```cpp
int nextOneForSure(int x, int y) {
    double d[y];
    d[0] = 1.0;
    for (int i = 1; i < y; i++) {
        d[i] = (d[i - 1] * (100 - x)) / 100.0;
    }

    double es = 0.0;
    for (int i = 0; i < y; i++) {
        for (int j = 0; j < y; j++) {
            double ccp = d[i] * d[j];
            if (i != y - 1) ccp *= static_cast<double>(x) / 100.0;
            if (j != y - 1) ccp *= static_cast<double>(x) / 100.0;

            es += (i + j + 2) * ccp;
        }
    }

    return static_cast<int>(std::ceil(es));
}

```

### Problem Number 28

```cpp
bool findsum(vector<int>a,int end,int tar){ 
int i=0; 
for(i=0;i<=end;i++){ 
    if(a[i]%2==0){ 
       for(int j=i;j<=end;j++){ 
           if(a[i]%2==0&&a[j]%2==0){ 
               int sum=a[i]+a[j]; 
               if(sum==tar){ 
                   return true; 
               } 
           } 
       } 
 
    } 
} 
    return false; 
} 
int maxEvenSum(int n, vector<int> a) { 
int i; 
int val=-1; 
for(i=0;i<n;i++){ 
    if(a[i]%2==0){ 
       bool b= findsum(a,i,a[i]); 
       if(b==true){ 
           val=max(val,a[i]); 
       } 
    } 
} 
int cnt=0; 
if(val==-1||val==0){ 
    for(i=0;i<n;i++){ 
        if(a[i]%2==0&&a[i]!=0){ 
            val=a[i]; 
        } 
        if(a[i]==0){ 
            cnt++; 
        } 
    } 
 
    if(cnt>0&&val!=-1&&val!=0){ 
    return val; 
    }     
 
return -1; 
} 
return val; 
}

```

### Problem Number 29

```cpp
#include <vector>

long long bitwiseInclusion(int n, std::vector<int> &a) {
    long long score = 0;

    for (int L = 0; L < n; L++) {
        int current_and = a[L];

        for (int R = L; R < n; R++) {
            current_and &= a[R];

            if (current_and != 0) {
                score += a[L];
            } else {
                break;  // If the AND becomes zero, no need to continue with this L.
            }
        }
    }

    return score;
}

```

### Problem Number 31

```cpp
int minimumTime(int x, int y, int z) {      
    int mx = max({x/2 + x%2, y/2 + y%2, z/2 + z%2});   
    int placementlelo = 3 * (mx - 1);      
    if(mx == z/2 + z%2){   
        placementlelo += 2;      
        } 
        else if(mx == y/2 + y%2){   
        placementlelo++;      
        }   
    return placementlelo + 30;  
    } 

```

### Problem Number 32

```cpp
int minimumOperations (int x, int y) {

        int ans = 1e9;

        for(int i = y; i <= y + 100; i++)
        {

                int cnt = 0;

                if(i == 1) 
                {

                 continue;

                }

                 int x1 = x;

                while(x1 > 0)
                {

                x1 /= i;

                cnt++;

                }

                ans = min(ans, cnt+ (i- y));

        }

        return ans;

}
```

### Problem Number 34

```cpp
int checkSequence(int A, int D, int X) { 
    if (D == 0) { 
        if (A == X) { 
            return 1; 
        } else { 
            return 0; 
        } 
    } 
 
    if ((X - A) % D == 0 && (X - A) / D >= 0) { 
        return 1; 
    }  
    else { 
        return 0; 
    } 
} 

```

### Problem Number 35

```cpp
string ninjaWantsHoliday(int n, int k, vector<int> &arr) {  
 int i,j;  
    sort(arr.begin(),arr.end());  
    for(i=0;i<n;i++){  
        int cnt=1;  
        for(j=i;j<i+k;j++){  
            if(arr[j+1]-arr[j]==1){  
                cnt++;  
            }  
            if(arr[j+1]-arr[j]!=1){  
                break;  
            }  
        }  
        if(cnt==k){  
            return "YES";  
        }  
    }  
    return "NO";  
}
```

### Problem Number 37

```cpp
string ninjaAndIdealGas(int  r, int o, int n, int t, int i) { 
    int a = n*t; 
    if(n>1000000)return "NO"; 
    if(r*o == a*i)return "YES"; 
    return "NO"; 
}
```

### Problem Number 17

```cpp
int maximumSquareDivisor(int n) {
 // Write your code here
 int maxSpeed = 1;
  for (int x=2; x<= sqrt(n); x++){
   if (n% (x*x)==0){
    maxSpeed=x;
   }
  } 
 return maxSpeed;
}
```
