# bsdatetime

[![PyPI version](https://badge.fury.io/py/bsdatetime.svg)](https://badge.fury.io/py/bsdatetime)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Pure Python library for Bikram Sambat (Nepali) calendar date & datetime operations.

## Features

- ✅ Convert between Gregorian (AD) and Bikram Sambat (BS) dates
- ✅ Format and parse BS dates with localized month/weekday names
- ✅ Comprehensive date validation and error handling  
- ✅ Calculate fiscal years, quarters, week numbers, date ranges
- ✅ No external dependencies - pure Python
- ✅ Type hints and comprehensive documentation
- ✅ Production-ready with security-focused design

## Installation

```bash
pip install bsdatetime
```

## Quick Usage

```python
import bsdatetime as bs  # new name
import datetime

# Convert AD to BS
ad_date = datetime.date(2024, 12, 25)
bs_date = bs.ad_to_bs(ad_date)
print(bs_date)  # (2081, 9, 9)

# Convert BS to AD  
bs_date = (2081, 5, 15)
ad_date = bs.bs_to_ad(*bs_date)
print(ad_date)  # 2024-08-30

# Format BS dates
formatted = bs.format_bs_date(2081, 5, 15, "%B %d, %Y")
print(formatted)  # भदौ 15, 2081

# Current BS date
current_bs = bs.utils.get_current_bs_date()
print(current_bs)
```

## API Highlights

| Function | Description |
|----------|-------------|
| `ad_to_bs(date)` | Convert Gregorian to BS date tuple |
| `bs_to_ad(y,m,d)` | Convert BS to Gregorian date |
| `format_bs_date(y,m,d, fmt)` | Format BS date with patterns |
| `parse_bs_date(str, fmt)` | Parse BS date from string |
| `is_valid_bs_date(y,m,d)` | Validate BS date |
| `utils.get_current_bs_date()` | Get current BS date |
| `utils.get_bs_fiscal_year(y,m)` | Get fiscal year |

## Supported Range

- **BS Years**: 1975 - 2100 (calendar data included)
- **Equivalent AD**: ~1918 - ~2043

## Django Integration

For Django model fields, install the companion package (will be updated to depend on `bsdatetime`):

```bash
pip install django-bikram-sambat
```

## License

MIT
