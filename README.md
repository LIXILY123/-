#include<iostream>
#include<ctime>
#include<vector>
#include<cstdlib>
using namespace std;

class test
{
private:
	vector<int>a;
	vector<int>::iterator p;
	int n, m, i;
public:
	test(int nn, int mm)
	{
		n = nn;
		m = mm;
		for (i = 0; i < n; ++i)
		{
			a.push_back(i + 1);
		}
		srand(time(0));
	}


	void turn()
	{
		int temp;
		for (i = 0; i < m; ++i)
		{
			temp = rand() % a.size();
			p = a.begin();
			cout << *(p + temp) << endl;
			a.erase(p + temp);

		}
	}
};

int main()
{
	test t(1000, 50);
	t.turn();
	return 0;
}
