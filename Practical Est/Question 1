// 76. Minimum Window Substring

class Solution {
public:
    string minWindow(string s, string t) {
        if (s.empty() || t.empty()) return "";

        unordered_map<char, int> need;

        for (char c : t) need[c]++;
        unordered_map<char, int> window;

        int have = 0;
        int req = need.size();
        int left = 0
    ;
        int min_len = INT_MAX;
        int min_start = 0;
        int m = s.size();
        for (int right = 0; right < m; ++right) {
            char c = s[right];
            window[c]++;
            if (need.count(c) && window[c] == need[c]) have++;
            
            while (have == req && left <= right) {
                if (right - left + 1 < min_len) {
                    min_len = right - left + 1;
                    min_start = left;
                }
                window[s[left]]--;
                if (need.count(s[left]) && window[s[left]] < need[s[left]]) have--;
                left++;
            }
        }
        return min_len == INT_MAX ? "" : s.substr(min_start, min_len);
    }
};
