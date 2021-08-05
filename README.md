#include <bits/stdc++.h>
using namespace std;

int main() {
	ios::sync_with_stdio(false);
	cin.tie(nullptr);

	int t;
	cin >> t;

	while (t--) {
		int n;
		cin >> n;

		vector<int> a(n);
		for (auto &x : a) cin >> x;

		int c0 = count(a.begin(), a.end(), 0);
		int c1 = count(a.begin(), a.end(), 1);
		int c2 = count(a.begin(), a.end(), -1);

		n -= c0;
		if (n <= 1) {
			cout << "yes\n";
			continue;
		}

		if (c2 > 0) {
			cout << (c2 == n || c1 + c2 != n ? "no" : "yes") << '\n';
		} else {
			cout << (c1 + 1 >= n ? "yes" : "no") << '\n';
		}
	}
	return 0;
}
