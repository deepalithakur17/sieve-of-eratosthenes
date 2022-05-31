# sieve-of-eratosthenes
Finding the number of prime numbers less then the given number by using sieve of eratosthenes technique
#include <bits/stdc++.h>
using namespace std;

bool is_prime(int n)
{

    for (int i = 2; i <= n / 2; i++)
    {
        if (n % i == 0)
        {
            return 0;
        }
    }
    return true;
}

int main()
{
    int i;
    cout<<"enter a number :"<<endl;
    cin >> i;
    cout<<"prime numbers are:"<<endl;
    vector<bool> prime(i, true);
    prime[0] = prime[1] = false;
    int count = 0;
    for (int h = 2; h < i; h++)
    {
        if (prime[h] != 1)
        {
            continue;
        }
        else
        {
            bool found = is_prime(h);
            if (found == true)
            {
                for (int j = h; j < i; j++)
                {
                    if (j % h == 0)
                    {
                        prime[j] = 0;
                    }
                }
                count++;
                cout << h << endl;
            }
        }
    }
    cout <<"numbers of prime numbers less then "<<i<<" is "<< count << endl;
}
