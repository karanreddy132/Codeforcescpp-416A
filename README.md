# Codeforcescpp-416A
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, num;
	int low = -2 * pow(10, 9);
	int high = 2 * pow(10, 9);
	string s, yn;
	cin >> n;
	for (int i = 0; i < n; i++) {
		cin >> s >> num >> yn;
		if ((s == ">" && yn == "Y") || (s == "<=" && yn == "N"))
			low = max(low, num + 1);
		else if ((s == "<" && yn == "Y") || (s == ">=" && yn == "N"))
			high = min(high, num - 1);
		else if ((s == ">=" && yn == "Y") || (s == "<" && yn == "N"))
			low = max(low, num);
		else if ((s == "<=" && yn == "Y") || (s == ">" && yn == "N"))
			high = min(high, num);
		if (low > high) {
			cout << "Impossible";
			return 0;
		}
	}
	cout << low;
	return 0;
}
