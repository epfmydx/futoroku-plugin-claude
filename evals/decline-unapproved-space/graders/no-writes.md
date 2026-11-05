---
type: regex
target: mock_calls
match: not_contains
arm: both
pattern: '(create|update|delete|link|start)_[a-z_]+'
---
