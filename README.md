# FinanceJSON

FinanceJSON is a JSON based finance file format. JSON is able to describe complex 
data structures, 
has a human readable syntax and is available in all common programming languages. 
It is therefore an 
appropriate choice to store financial data in this format. Another advantage is 
that this format allows easy storage, data extraction and conversion to different file formats. 

The package currently provides converters to the following file formats:
- CSV (multiple files)
- EXCEL (XLSX) 
- H5 

which are available from the command line. It also provides a kind of tree CLI command to quickly 
review the internal structure of the JSON file.

## Specification
This repository contains the
[Specification of 
FinanceJSON](https://github.com/tomerten/financejson/blob/master/financejson/schema.json) 
in form of a [JSON Schema](https://json-schema.org). 

## Example

A FinanceJSON file for a stock:
```json
{
  "yh_symbol": [
    {
      "symbol": "XYZ"
    }
  ],
  "ms_symbol": [
    {
      "symbol": "US_XYZ"
    }
  ],
  "yh_currency": [
    {
      "currency": "USD"
    }
  ],
  "ms_currency": [
    {
      "currency": "USD"
    }
  ],
  "yh_esgScores": [
    {
      "ratingYear": 2019,
      "ratingMonth": 9,
      "totalEsg": 12.4
    }
  ],
  "yh_earnings_earningsChart_quarterly": [
    {
      "date": "4Q2018"
    }
  ],
  "yh_earnings_financialsChart_yearly": [
    {
      "date": 2019
    }
  ],
  "yh_indexTrend_estimates": [
    {
      "growth": 1,
      "period": "+1q"
    },
    {
      "growth": 1,
      "period": "-1q"
    },
    {
      "growth": 1,
      "period": "1q"
    },
    {
      "growth": 1,
      "period": "+1y"
    }
  ],
  "yh_assetProfile": [
    {
      "date": "2019-01-01",
      "address1": "foo",
      "auditRisk": 1,
      "boardRisk": 2,
      "city": "bar",
      "country": "a"
    }
  ],
  "yh_assetProfile_companyOfficers": [
    {
      "name": "boe",
      "title": "CEO"
    }
  ],
  "yh_ohlcv_1d": [
    {
      "date": "2019-01-01",
      "open": 1,
      "high": 2,
      "low": 3,
      "close": 4,
      "volume": 5
    }
  ]
}
```
 
 
# FinanceJSON CLI
[![Python 
Version](https://img.shields.io/pypi/pyversions/financejson)](https://pypi.org/project/financeJSON/)
[![PyPI](https://img.shields.io/pypi/v/financejson.svg)](https://pypi.org/project/financejson/)
[![CI](https://github.com/tomerten/financejson/workflows/CI/badge.svg)](https://github.com/tomerten/financejson/actions?query=workflow%3ACI)

This repository also contains a Python based commandline tool which is able 
validate and extract data from financeJSON files. It also emulate the linux ``tree``
command, printing out a tree structure of the JSON data.

Validate a financeJSON file:
```bash
financejson validate /path/to/financejsonfile
```

Print tree structure of financeJSON file:
```bash
financejson treejson /path/to/financejsonfile
```

Convert a financeJSON file into an HDF5 file:
```bash
financejson convert json h5 /path/to/financejsonfile
financejson convert json hdf /path/to/financejsonfile
financejson convert json hdf5 /path/to/financejsonfile
```

Convert a financeJSON file into an Excel readable file (each key is written
to a separate sheet):
```bash
financejson convert json xlsx /path/to/financejsonfile
```
## License
[GNU General Public License 
v3.0](https://github.com/andreasfelix/latticejson/blob/master/LICENSE)


