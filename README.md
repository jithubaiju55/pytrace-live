# pytrace-live

A lightweight Python CLI tool that traces function execution in real-time, showing execution times and highlighting slow functions as your code runs.

## Installation

```bash
pip install pytrace-live
```

## Usage

Basic usage:

```bash
pytrace-live script.py
```

With custom slow threshold (default is 100ms):

```bash
pytrace-live script.py --threshold 200
```

## Example Output

```
→ load_config()              6 ms
→ connect_db()             420 ms  ⚠ SLOW
→ fetch_users()           1310 ms  🚨 VERY SLOW
→ process_data()            45 ms
→ save_results()           180 ms  ⚠ SLOW
```

**Color coding:**

- Green: Normal execution (< threshold)
- Yellow: Slow (≥ threshold) with ⚠ SLOW marker
- Red: Very slow (≥ 5× threshold) with 🚨 VERY SLOW marker

## Why Use This?

- **Zero code changes**: Just run your script through pytrace-live
- **Live feedback**: See performance bottlenecks as they happen
- **Minimal overhead**: Uses Python's built-in profiling hooks
- **Clean output**: Only shows your functions, filters out internal/stdlib calls

Perfect for quick performance checks during development without setting up complex profiling tools.

## Requirements

- Python 3.9 or higher
- `rich` (for terminal formatting)

## License

MIT License - see LICENSE file for details
