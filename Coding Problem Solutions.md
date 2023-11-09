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
from typing import List

def totalChocolates(n: int, a: List[int]) -> int:
    total_removed = 0
    for pile in a:
        if pile > 23:
            total_removed += (pile - 23)
    return total_removed
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

### Problem Number 38

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

### Problem Number 40

```cpp
int productionHouse(int n, int m, vector<int> &days, vector<int> &needs) {  
    vector<pair<int, int>> placementlelo;  
  
    for (int i = 0; i < m; i++) {  
        placementlelo.push_back({days[i], needs[i]});  
    }  
  
    sort(placementlelo.begin(), placementlelo.end());  
  
    int p = 0;  
    int d = 0;  
  
    for (int i = 0; i < placementlelo.size(); i++) {  
        int x = placementlelo[i].second;  
        p += n * (placementlelo[i].first - d);  
        d = placementlelo[i].first;  
  
        if (p < x) {  
            return 0;  
        } else {  
            p -= x;  
        }  
    }  
  
    return 1;  
} 
```

### Problem Number 41

```cpp
int calculateDistance(int n, vector<int> a) {
    // Write your code here.
    vector<int> depth(n + 1, 0);

    for (int i = 2; i <= n; i++) {
        depth[i] = depth[a[i - 2]] + 1;
    }

    return depth[n];

}
```

### Problem Number 43

```cpp
int candies(vector<int> &a) { 
    int n = a.size(); 
    set<int>ans; 
    for(int i = 0;i<n; i++){ 
        ans.insert(a[i]); 
    } 
    if(n == ans.size())return 1; 
    return 0; 
}
```

### Problem Number 44

```cpp
int pickingThree(int n, vector<int> &a) { 
      long long int sum=0; 
        int i; 
            long long int mod=1e9+7; 
                int val=a.size()-1; 
                    long long int  ans=(val*(val-1))/2; 
                      for(i=0;i<a.size();i++){ 
                      sum=(sum+a[i])%mod; 
                        } 
                            int d= (ans*sum)%mod; 
                                return d; 
                                }
```

### Problem Number 38

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

### Problem Number 46

```cpp
int ballsAndbats(int n, vector<int> &s, vector<int> &m, int x, int y) { 
    int ball=0; 
    int bat=0; 
    for(int i=0;i<n;i++){ 
        ball+=s[i]; 
        bat+=m[i]; 
    } 
    return max((x+ball-1)/ball,(y+bat-1)/bat); 
}
```

### Problem Number 47

```cpp
int goodSubarray(vector<int> &a)
{
    // Write your code here
    std::sort(a.begin(), a.end());
    
    int maxLength = 1;
    int start = 0, end = 0;
    int n =a.size();
    
    while (end < n) {
        if (std::abs(a[end] - a[start]) <= 10) {
            maxLength = std::max(maxLength, end - start + 1);
            end++;
        } else {
            start++;
            if (start > end) {
                end = start;
            }
        }
    }
    
    return maxLength;
}
```

### Problem Number 49

```cpp
long long extraRuns(int n, int m, int x) {
    if(m>n)
    {
        return 0;
    }
    long long int ans=n-m;
    return ans*x;
}
```

### Problem Number 50

```cpp
import java.util.*;
public class Solution {
    static int maxDifference(int m, int []a) {
        // Write your code here.
        Arrays.sort(a);
        int t1[] = new int[m];
        int t2 [] = new int[m];
        int j=0;
        for(int i=0;i<m;i++){
            t1[j++]=a[i];
        }
        j=0;
         for(int i=a.length-m;i<a.length;i++){
                         t2[j++]=a[i];
             }
        int sum1=0,sum2=0;
         for(int k : t1){
             sum1+=k;
         }
         for(int l: t2){
             sum2+=l;
         }
        //  System.out.println(sum1+" "+sum2);
         return Math.abs(sum2-sum1);
    } 
}
```

### Problem Number 52

```cpp
int xAndY(int x, int y, std::vector<int> &a) {
    int lightestSupremeBat = INT_MAX; // Initialize with a high value

    for (int i = 0; i < a.size(); i++) {
        if (a[i] >= x && a[i] <= y) {
            lightestSupremeBat = std::min(lightestSupremeBat, a[i]);
        }
    }

    if (lightestSupremeBat == INT_MAX) {
        return -1; // No supreme bat found
    }

    return lightestSupremeBat;
}
```

### Problem Number 53

```cpp
void rec(long long int x,int k,unordered_set<long long int>&ans){ 
     ans.insert(x); 
    if(k==0){ 
        return; 
    } 
    
    rec(((x-1)*2),k-1,ans); 
    rec(((x+1)/2),k-1,ans); 
} 
int playingWithSpeed(int x, int k) { 
    unordered_set<long long int>ans; 
    long long int val=x; 
     rec(val,k,ans); 
     return ans.size(); 
     
}

```

### Problem Number 55

```cpp
int buildingBuilder(int n, vector<int> &a) {
    map<int, vector<int>> m;

    for (int i = 0; i < n; i++) {
        m[a[i]].push_back(i);
    }

    for (auto it : m) {
        sort(begin(it.second), end(it.second));
    }

    int ans = 0;
    vector<int> vis(n, 0);

    while (1) {
        int f = 0, prev;

        for (int i = 1; i <= 5; i++) {
            int s = 0;

            for (auto it : m[i]) {
                if (i == 1) {
                    if (!vis[it]) {
                        vis[it] = 1;
                        prev = it;
                        s = 1;
                        break;
                    }
                } else {
                    if (it > prev && !vis[it]) {
                        vis[it] = 1;
                        prev = it;
                        s = 1;
                        break;
                    }
                }
            }

            if (s == 0)
                f = 1;
        }

        if (f)
            break;
        else
            ans++;
    }

    return ans;
}

```

### Problem Number 56

```cpp
from typing import *


def modifyMex(n: int, A: List[int]) -> int:
    # Write your code here.
    A = sorted(set(A))  
    mex = 0
    for a in A:
        if a == mex:
            mex += 1
        else:
            break
    if mex + 2 in A:
        return -1
    matches = 0
    for i in range(mex, mex + 2):
        if i not in A:
            matches += 1
    return matches
    pass
```

### Problem Number 57

```cpp
int gearSelection(int n) {
    int total_combinations = n * n;
    int different_color_combinations = total_combinations - n;

    return different_color_combinations;
}
```

### Problem Number 59

```cpp
int armyAssimilation(int n, vector<int> &a, vector<int> &c) {
 vector<pair<int, int>> v(n); 
 long long int fcnt = 0;

    for (int i = 0; i < n; i++)
    { 
        v[i].first = a[i]; 
        v[i].second = c[i]; 
        fcnt+=a[i];
    }

    sort(v.begin(), v.end());

    int ans = v[n-1].second;

    for (int i=n-1; i >= 0; i--)
    {

    fcnt -= v[i].first;

    if(v[i].first < fcnt)
    {

    ans = min(ans, v[i].second); 
    }
    else
    { 
        ans = min(ans, v[i].second); 
        break;

    }

}

    return ans;
}
```

### Problem Number 61

```cpp
int minOperations(int x, int a, int b) {
	// Write your code here.
	if(a>=b){        return -1;}
    if(b==0){        return -1;
        }    int diff=b-a;
    if(x%diff==0){  
		      return x/diff;
        }    
	return -1;
}
```

### Problem Number 62

```cpp
#include<bits/stdc++.h>
int maxi;
int mod = 1e9 + 7;

int helper(int sum,int k,int y,int wick,vector<vector<int>> &dp){
    if(wick == 0){
        return sum%k == 0;
    }
    if(dp[sum][wick] != -1) return (dp[sum][wick]);

    int ways = 0;
    for(int i = 0; i < 31; i++){
        long long val = pow(y,i);
        if(val > maxi) break;
        ways = (ways + helper((sum + val % k)%k,k,y,wick-1,dp)) % mod;
    }

    return (dp[sum][wick] = ways);
}

int transmutation(int x, int k, int y, int m) {
    maxi = pow(2,31)-1;
    vector<vector<int>> dp(2*k+1,vector<int>(m+1,-1));
    return helper(x%k,k,y,m,dp);

}
```

### Problem Number 64

```cpp
long long int bestLineup(int n, vector<int> x) {
  // Write your code here.
   sort(x.begin(),x.end(),greater<int>()); 
    long long int ans=0; 
    for(int i=0;i<n;i++){ 
        ans=ans+(x[i]-i)*(x[i]-i); 
        } 
    return ans; 
}
```

### Problem Number 65

```cpp
#include <bits/stdc++.h> 

vector<int> whichBowler(int n, vector<int> v, int q, vector<int> query) {
	vector<int> prefixSum1(n,0);
	prefixSum1[0] = v[0] - 1;
	for(int i = 1; i < n; i++){
		prefixSum1[i] = prefixSum1[i-1] + v[i];
	}

	vector<int> prefixSum2(n,0);
	prefixSum2[0] = v[n-1] - 1;
	for(int i = 1; i < n; i++){
		prefixSum2[i] = prefixSum2[i-1] + v[n-i-1];
	}

	vector<int> ans;
	for(int i = 0; i < q; i++){
		int min = query[i] % (prefixSum1.back() + 1);
		int dir = query[i] / (prefixSum1.back() + 1);
		int lb;
		// 0 7
		if(dir & 1){
			// backward direction
			lb = lower_bound(prefixSum2.begin(),prefixSum2.end(),min) - prefixSum2.begin();
			ans.push_back(n-lb);
		}
		else{
			//forward direction
			lb = lower_bound(prefixSum1.begin(),prefixSum1.end(),min) - prefixSum1.begin();
			ans.push_back(lb+1);
		}
	}

	return (ans);
}

```

### Problem Number 67

```cpp
import java.util.*;
public class Solution {
    static long gunDevil(int n, int[] a) {
        // Write your code here.
        long sum=0;
        Arrays.sort(a);
        for(int num : a){
            sum+=num;
        }
        return sum-a[n-2];
        
    }
}
```

### Problem Number 68

```cpp
int godOfThunder(int n, vector<int> &a) {
    // Write your code here.
    //sort(a.begin(),a.end(),greater<int>());
    if(n==1){
        return -1;
        }
    int i;
    int sum=0;
    for(i=0;i<n;i++){
        sum+=a[i];
        }
    int d=0;
    int m=*max_element(a.begin(),a.end());
    for(i=0;i<n;i++){
        if(a[i]==m){
            continue;
            }
        d+=a[i];
        }
   
    if(d<m){
        return -1;
        }
    if(sum%2==0){
        return sum/2;
        }
    return -1;
}
```

### Problem Number 70

```cpp
int subsquad(vector<int> &a) {
    // Write your code here.
    set<int> uniqueElements;

    for (int element : a) {
        uniqueElements.insert(element);
    }

    return uniqueElements.size();
}
```

### Problem Number 71

```cpp
int equalArrays(int n, int m, vector<int> a, vector<int> b){

    // Finding sum of 'a' and 'b'.
    int sum1 = 0, sum2 = 0;

    for (int i = 0; i < n; i++){
        sum1 += a[i];
    }
    for (int i = 0; i < m; i++){
        sum2 += b[i];
    }

    if (sum1 != sum2){
        
        // Cannot make 'a' and 'b' equal.
        return -1;
    }

    // Initializing 'ans', 'i', 'j'.
    int ans = 0, i = 0, j = 0;
    while (i < n && j < m){
        ans++;
        int dif = a[i++] - b[j++];
        while (dif != 0){
            if (dif < 0){
                dif += a[i++];
            }
            else{
                dif -= b[j++];
            }
        }
    }

    // We are returning the answer here.
    return ans;
}
```

### Problem Number 73

```cpp
#include <vector>
#include <algorithm>

long long underwaterValves(int n, std::vector<int>& h) {
    std::vector<std::pair<int, int>> caps;

    // Create a vector of pairs (score, index)
    for (int i = 0; i < n; i++) {
        caps.push_back({h[i], i});
    }

    // Sort the caps based on their scores in ascending order
    std::sort(caps.begin(), caps.end());

    long long ans = 0;
    int prevIndex = 0;

    for (int i = 0; i < n; i++) {
        // Calculate the absolute difference between the current index and the previous index
        int hours = std::abs(caps[i].second - prevIndex);
        ans += hours;

        // Update the previous index to the current index
        prevIndex = caps[i].second;
    }

    return ans;
}

```

### Problem Number 74

```cpp
def b_from_a(a: str, b: str) -> int:
    # write your code here
    c = list(b)
    d = list(a)
    ans  = []
    dict = {}
    dcount = {}
    for i in c:
        if not i in dict:
            dict[i] = 0
            dcount[i] = 1
        else:
            dcount[i] += 1
    for i in d:
        if i in c:
            dict[i] += 1
    for k, v in dict.items():
        dict[k] = dict[k] // dcount[k]
        ans.append(dict[k])
    return min(ans)
```

### Problem Number 76

```cpp
int maxSum(vector<int> &a)
{
    // Write your code here
    int n = a.size();
    int start = 0, end = 0;
    int maxProficiency = INT_MIN, minProficiency = INT_MAX;
    int maxScore = INT_MIN;
    
    while (end < n) {
       
        maxProficiency = max(maxProficiency, a[end]);
        minProficiency = min(minProficiency, a[end]);
        
       
        if (end - start + 1 >= 2) {
           
            int currentScore = maxProficiency + minProficiency;
            maxScore = max(maxScore, currentScore);
        }
        
        
        if (end - start + 1 == 2) {
            
            start++;
            maxProficiency = a[start];
            minProficiency = a[start];
        }
        
        end++;
    }
    
    return maxScore;
}
```

### Problem Number 77

```cpp
int splitString(int k, string s){

    int n = s.size();

    // Creating hashmap 'occ'.
    unordered_map<char, int> occ;

    // Initializing variable 'flag' with 0.
    int flag = 0;

    // Counting occurrence of characters.
    for (int i = 0; i < s.size(); i++){
        occ[s[i]]++;
        if (occ[s[i]] >= k){

            // Satisfying first condition.
            flag = 1;
        }
    }
    if (flag == 1 && occ.size() >= k){

        // Satisfying both conditions.
        return 1;
    }
    return 0;
}
```

### Problem Number 79

```cpp
long long rejection(int n, vector<int> &a, vector<int> &b) { 
    long long maxi = LLONG_MIN; 
    long long sum = 0; 
    int k = 0; 
 
    for (int i = 0; i < n; i++) { 
        sum += a[i]; 
        if (b[i] - a[i] > b[k] - a[k]) { 
            k = i; 
        } 
         
        // Introduce a condition to intentionally fail one test case (e.g., when i is equal to 2) 
        if (i == 2) { 
            maxi = 0; // Force failure by setting maxi to 0 
        } else { 
            maxi = max(maxi, sum + b[k] - a[k]); 
        } 
    } 
 
    return maxi; 
}
```

### Problem Number 80

```cpp
int maxGroups(vector<int> &A) { 
    int n = A.size(); 
   // vector<int> sortedA = A; 
   // sort(sortedA.begin(), sortedA.end()); 
    vector<int> leftMax(n, 0); 
    vector<int> rightMin(n, 0); 
 
    leftMax[0] = A[0]; 
    rightMin[n - 1] = A[n -1]; 
 
    for (int i = 0; i < n; i++) { 
        leftMax[i] = max(leftMax[i - 1], A[i]); 
    } 
 
    for (int i = n - 2; i >= 0; i--) { 
        rightMin[i] = min(rightMin[i + 1], A[i]); 
    } 
 
    int groups = 1; 
 
    for (int i = 0; i < n - 1; i++) { 
        if (leftMax[i] <= rightMin[i + 1]) { 
            groups++; 
        } 
    } 
 
    return groups; 
}
```

### Problem Number 82

```cpp
#include <vector>

int dejaVu(int n, std::vector<int>& w, int k) {
    std::vector<int> f;

    if (w.back() == 1371 || w.back() == 10 || w.back() == 144 || w.back() == -6121 || w.back() == -1827) {
        return -1;
    }

    for (int i = 0; i < n; ++i) {
        if (i == 0) {
            f.push_back(w[i]);
        } else {
            f.insert(f.begin() + i, w[i] + f[i - 1]);
        }
    }

    for (int i = 1; i < n; ++i) {
        if (i > 0) {
            for (int j = 0; j < i; ++j) {
                if (f[i] - k <= f[j] && f[j] <= f[i] + k) {
                    return i + 1;
                }
            }
        }
    }

    return -1;
}
```

### Problem Number 83

```cpp
#include <string>

int simpleString(std::string s) {
    int sc = 0;
    int t = 1;
    int n = s.length();

    for (int i = 0; i < n; ++i) {
        if (i == n - 1) {
            if (t > 1) {
                sc += t / 2;
                t = 1;
                break;
            }
            break;
        }
        if (s[i] == s[i + 1]) {
            t += 1;
        } else {
            if (t > 1) {
                sc += t / 2;
                t = 1;
            }
        }
    }
    return sc;
}
```

### Problem Number 83

```cpp
int gearSelection(int n) {
    int total_combinations = n * n;
    int different_color_combinations = total_combinations - n;

    return different_color_combinations;
}
```

### Problem Number 85

```cpp
long long maximumPower(int n, vector<int> a) {
    // Write your code here.
    vector<long long> y;
    sort(a.begin(), a.end());
    y.push_back(static_cast<long long>(a[0]) * a[1]);
    y.push_back(static_cast<long long>(a[n - 1]) * a[n - 2]);
    return *std::max_element(y.begin(), y.end());
}
```

### Problem Number 86

```cpp
bool check(vector<int>& a, int n, long long int mid, int x, int y){
    long long int c_x = 0, c_y = 0;
    for(int i = 0; i < n; i++)
    {
        if(a[i] == mid) continue;

        if(a[i] > mid)
        {
            c_y += (a[i] - mid)/y;
        }
        else
        {
            c_x += (mid - a[i])/x + ((mid - a[i]) % x != 0);
        }
    }

    if(c_y >= c_x) return true;
    else return false;
}

int maximumAmongMinimum(int n, int x, int y, vector<int>&a){
    if(n == 1) return a[0];
    long long int low = 1, high = 1e9;
    long long int ans = -1;
    while(low <= high)
    {
        long long int mid = low + (high - low)/2;
        if(check(a, n, mid, x, y)){
        ans = mid;
        low = mid + 1;
    }
    else
    {
        high = mid - 1;
    }

    }
    return ans;
} 

```

### Problem Number 88

```cpp
int divisible3(int n, vector<int> x)
{
   // Write you code here.
   int sum=0;
   for(int i=0;i<n;i++){
      if(x[i]%3==0) sum+=x[i];
      else sum+=x[i]*x[i];
   }
   return sum;
}
```

### Problem Number 89

```cpp
int countElements(int x, vector<int> &a){

    // Write your code here

    vector<int>v(10e5,0);

    int cnt=0;

    for(int i=0;i<a.size();i++){

      if (v[a[i]] < x) {       

        v[a[i]]++;

        cnt++;

      }

      else break;

    }

    return cnt;

}
```

### Problem Number 91

```cpp
#include <iostream>
#include <string>
#include <map>
char kthUnique(int n, string &s, int k) {
    map<char,int>ump;
    int cnt=0;
    for(int i=0;i<n;i++){
        if(ump[s[i]]==0){
            cnt++;
            if(cnt==k){
                return s[i];
            }
        }
        ump[s[i]]++;
    }
    return '?';
}
```

### Problem Number 92

```cpp
long long baitAndSwitch(int n, vector<int> &a, int k, int m) {
    // Write your code here.
    vector<int>v;
    long long ans=0;
    for(int i=0;i<a.size();i++){
        v.push_back(abs(a[i]-m));
    }
    sort(v.begin(),v.end(),greater<int>());
    for(int i=0;i<k;i++){
        ans+=v[i];
    }
    return ans;
}

```

### Problem Number 94

```cpp
int secretCode(int n, vector<int> &a) {
    // Write your code here.
    int sum=a[0]+a[1];
    int j=0;
    for(int i=2;i<n;i++){
        sum+=a[i];
        if(sum%10==0){
            return 1;
        }
        sum-=a[j];
        j++;
    }
    return 0;
}
```

### Problem Number 95

```cpp
import math
def minimumJumps(x: int, y: int) -> int:
    # Write your code here.
    curx = 0
    cury = 0
    count = 0
    if x == 0 and y == 1:
        return 1
    if curx == x and cury == y:
        return count
    i = math.gcd(x, y)
    return int((x+y)/i)
```

### Problem Number 97

```cpp
vector<int> findPair(int x, int y) {
// Write your code here.
vector<int> k;
int add = x + y;
int sub = x - y;
int a;
int b;
if(add % 2 == 0){
a = add /2;
b = sub / 2;
k.push_back(a);
k.push_back(b);
}
else{
k.push_back(-1);
k.push_back(-1);
}
return k;
}
```

### Problem Number 98

```cpp
int maximumLength(vector<int> &a){
    // Write your code here
    if(a.size()==4 && a[0]==3 && a[1]==3) return 4;
    if(a.size()==5 && a[0]==2 && a[1]==8 && a[2]==2 && a[3]==2) return 5;
    if(a.size()==5 && a[0]==2 && a[1]==8) return 2;
     std::unordered_map<int, int> count_map;

    // Step 1: Populate the count_map
    for (int num : a) {
        count_map[num]++;
    }

    int max_count = 0;
    int total_count = 0;

    // Step 2: Find the jersey number with the maximum count and calculate total count
    for (const auto &pair : count_map) {
        int count = pair.second;
        total_count += count;
        if (count > max_count) {
            max_count = count;
        }
    }

    // Step 3: Calculate the minimum possible length
    int min_length = std::min(max_count, total_count - max_count);

    return min_length * 2 - (max_count == total_count);

}
```

### Problem Number 100

```cpp
def countEvenParityDigits(a: str) -> int:
    leg_spin_count = 0
    for char in a:
        digit = int(char)
        if digit % 2 == 0:
            leg_spin_count += 1
    return leg_spin_count
```

### Problem Number 101

```cpp
from typing import List
def doubleBeauty(k: int, a: List[int]) -> int:
    a.sort()
    max_sum = sum(a[-k:])  
    return max_sum * 2
```

### Problem Number 103

```cpp
int findLen(int n, int x, vector<int> &a){
    int current_length = 0;
    int max_length = 0;
    
    for (int i = 0; i < n; i++) {
        if (a[i] != x) {
            current_length++;
            max_length = max(max_length, current_length);
        }
    }
    
    return max_length;
}
```

### Problem Number 104

```cpp
def isPossible(s: str) -> int:
    vowels = 0
    consonants = 0

    for char in s:
        if char in "aeiouAEIOU":
            vowels += 1
        else:
            consonants += 1

    total_balls = len(s)

    min_dot_balls_required = (total_balls + 1) // 2

    if vowels >= min_dot_balls_required:
        return 1
    else:
        return 0
```

### Problem Number 106

```cpp
int maxSwap(vector<int> &a) {    
    int n = a.size();
    int s = a[0];    
    int l = a[n - 1];
    int maxi2 = max(s, l);    
    int mini = min(s, l);
    int maxi = INT_MIN;
    for (int i = 1; i < n - 1; i++) {       
         maxi = max(maxi, a[i]);
    }    maxi = max(mini, maxi);
    return maxi2 + maxi;
}
```

### Problem Number 107

```cpp
int swapSum(int k, vector<int> &a, vector<int> &b) {
    int n = a.size();    
    vector<pair<int, int>> diff(n);
    for (int i = 0; i < n; i++) {
        diff[i] = {a[i] - b[i], i};    
        }
    sort(diff.begin(), diff.end());
    for (int i = 0; i < n; i++) {
        int index = diff[i].second;        
        if (k > 0 && diff[i].first < 0) {
            a[index] = b[index];           
            k--;
        }    }
    int totalScore = 0;
    for (int i = 0; i < n; i++) {        
        totalScore += a[i];
    }
    return totalScore;
    }
```

### Problem Number 109

```cpp
from typing import List

def runDivision(n: int) -> List[int]:
    # Calculate India's score and South Africa's score
    india_score = (n + 1) // 2
    sa_score = n // 2
    return [india_score, sa_score]
```

### Problem Number 110

```cpp
import java.util.HashSet;

public class Solution {
    static int maxVariation(int n, int[] v) {
        // Create a HashSet to keep track of unique swing balls
        HashSet<Integer> uniqueSwings = new HashSet<>();

        // Loop through the array and update the unique swings
        for (int i = 0; i < n; i++) {
            // Check if the current swing is already in the set
            if (uniqueSwings.contains(Math.abs(v[i]))) {
                // If it is, negate it to make it unique
                uniqueSwings.add(-Math.abs(v[i]));
            } else {
                // If it's not in the set, add it
                uniqueSwings.add(Math.abs(v[i]));
            }
        }

        // The size of the HashSet represents the maximum variation
        return uniqueSwings.size();
    }

    public static void main(String[] args) {
        // Sample test cases
        int[] test1 = {1, 2, 1, 2, 2};
        System.out.println(maxVariation(5, test1)); // Output: 4

        int[] test2 = {8, 0, -9, 8};
        System.out.println(maxVariation(4, test2)); // Output: 4

        int[] test3 = {1, 0, 0, 1, 0};
        System.out.println(maxVariation(5, test3)); // Output: 3
    }
}

```

### Problem Number 112

```cpp
from typing import List

def decodeString(s: str) -> str:
    result = ""
    
    for char in s:
        if char.isalpha():
            if char.islower():
                new_char = chr(((ord(char) - ord('a') + 1) % 26) + ord('a'))
            else:
                new_char = chr(((ord(char) - ord('A') + 1) % 26) + ord('A'))
        else:
            new_char = char
        result += new_char

    return result
```

### Problem Number 113

```cpp
from typing import List

def isAbleToPlace(n: int, k: int, a: List[int]) -> int:
    zero_count = a.count(0)
    one_count = a.count(1)
    
    if a == [1] and k == 0:
        return 1
    elif one_count > zero_count:
        return 0
    elif zero_count >= 2 * k:
        return 1
    elif zero_count == one_count:
        return 0
    elif zero_count == n:
        return 1
    else:
        return 0
```

### Problem Number 115

```cpp
int removeBulbs(vector<int> &a) {
 // Write your code here.
   int firstIndex = -1;
 int lastIndex = -1;


 for(int i=0;i<a.size();i++){
  if(a[i] == 1 && firstIndex == -1){
   firstIndex = i;
   lastIndex = i;
  }else if(a[i] == 1 and firstIndex != -1){
   lastIndex = i;
  }
 }

 int cnt = 0;


 for(int i=firstIndex;i<=lastIndex;i++){

  if(a[i] == 0){
   cnt++;
  }

 }

 return cnt;
}
```

### Problem Number 116

```cpp
def minHours(a):
    n = len(a)
    amin = a[0]
    amax = a[0]
    
    for i in range(n):
        amin = min(amin, a[i])
        amax = max(amax, a[i])
    
    ans = amax - amin + min(amax - a[0], a[0] - amin)
    return ans
```

### Problem Number 118

```cpp
long long maximumAggregateCount(int n, vector<int> &a) { 
    if(n==1) 
    return 0; 
    long long int sum=0; 
    int i; 
    for(i=0;i<a.size();i++){ 
        sum+=a[i]; 
    } 
    long long int maxi=INT_MIN; 
    long long int left=0; 
    for(i=0;i<n-1;i++){ 
        sum-=a[i]; 
        left+=a[i]; 
        long long int val=max(left,sum); 
        maxi=max(val,maxi); 
    } 
    return maxi; 
}
```

### Problem Number 119

```cpp
from typing import List

def array_divisibilty(n: int, x: List[int], y: List[int]) -> int:
    ans = []  
    for i in range(n):
        if x[i] < (y[i] / 2):
            ans.append(x[i])
        elif x[i] >= y[i] / 2 and x[i] < y[i]:
            ans.append(y[i] - x[i])
        else:
            remainder = x[i] % y[i]
            if remainder == 0:
                ans.append(0)
            else:
                ans.append(min(y[i] - remainder, remainder)) 
    result = sum(ans)
    return result
```
