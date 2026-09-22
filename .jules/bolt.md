## 2024-10-18 - [In-place string operations]
**Learning:** When adding substrings or concatenated strings to a std::vector<std::string>, utilizing vector.emplace_back(original_str, pos, count) or a push_back(prefix) followed by back().append(str, pos, count) effectively prevents intermediate temporary string allocations.
**Action:** Always favor these in-place initialization and appending patterns over combining std::string::substr() with concatenation inside vector push_back calls.
