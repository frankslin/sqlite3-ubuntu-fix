# SQLite3 Ubuntu Fix

Fix for nested JOIN segfault in Ubuntu 24.04 LTS sqlite3 package.

## Bug Report
- **Ubuntu Bug**: https://bugs.launchpad.net/bugs/2087772
- **Upstream Fix**: https://github.com/sqlite/sqlite/commit/74851f66811854c

## Issue
SQLite3 crashes with segmentation fault when executing queries with LEFT JOIN 
nested inside INNER JOIN structures.

## Base Version
- Package: `sqlite3 3.45.1-1ubuntu2.5`
- Ubuntu: 24.04 LTS (Noble)
- Source: https://launchpad.net/ubuntu/+source/sqlite3/3.45.1-1ubuntu2.5

## Changes
- [ ] Add autopkgtest for nested JOIN regression
- [ ] Apply upstream fix (if needed)

## Testing
```bash
./debian/tests/nested-joins
```

## Building
```bash
debuild -us -uc
```
