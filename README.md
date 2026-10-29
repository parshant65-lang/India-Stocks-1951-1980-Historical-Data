# India-Stocks-1951-1980-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1951 to 1980)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1951-1980-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1951 to 1980)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1951 | `ARHAM` | Arham Technologies Limited | `ARHAM.NS` |
| 1952 | `INDTONER` | Indian Toners & Developers Limited | `INDTONER.NS` |
| 1953 | `PVP` | PVP Ventures Limited | `PVP.NS` |
| 1954 | `PVSL` | Popular Vehicles and Services Limited | `PVSL.NS` |
| 1955 | `PYRAMID` | Pyramid Technoplast Limited | `PYRAMID.NS` |
| 1956 | `QMSMEDI` | QMS Medical Allied Services Limited | `QMSMEDI.NS` |
| 1957 | `QPOWER` | Quality Power Electrical Equipments Limited | `QPOWER.NS` |
| 1958 | `QUADFUTURE` | Quadrant Future Tek Limited | `QUADFUTURE.NS` |
| 1959 | `QUESS` | Quess Corp Limited | `QUESS.NS` |
| 1960 | `QUICKHEAL` | Quick Heal Technologies Limited | `QUICKHEAL.NS` |
| 1961 | `QUINT` | Quint Digital Limited | `QUINT.NS` |
| 1962 | `QUINTEGRA` | Quintegra Solutions Limited | `QUINTEGRA.NS` |
| 1963 | `RACE` | Race Eco Chain Limited | `RACE.NS` |
| 1964 | `RACLGEAR` | RACL Geartech Limited | `RACLGEAR.NS` |
| 1965 | `RADAAN` | Radaan Mediaworks India Limited | `RADAAN.NS` |
| 1966 | `RADHIKAJWE` | Radhika Jeweltech Limited | `RADHIKAJWE.NS` |
| 1967 | `RADIANTCMS` | Radiant Cash Management Services Limited | `RADIANTCMS.NS` |
| 1968 | `RADIOCITY` | Music Broadcast Limited | `RADIOCITY.NS` |
| 1969 | `RAIN` | Rain Industries Limited | `RAIN.NS` |
| 1970 | `RAJESHEXPO` | Rajesh Exports Limited | `RAJESHEXPO.NS` |
| 1971 | `RAJMET` | Rajnandini Metal Limited | `RAJMET.NS` |
| 1972 | `RAJOOENG` | Rajoo Engineers Limited | `RAJOOENG.NS` |
| 1973 | `RAJPALAYAM` | Rajapalayam Mills Limited | `RAJPALAYAM.NS` |
| 1974 | `RAJRATAN` | Rajratan Global Wire Limited | `RAJRATAN.NS` |
| 1975 | `RAJRILTD` | Raj Rayon Industries Limited | `RAJRILTD.NS` |
| 1976 | `RAJSREESUG` | Rajshree Sugars & Chemicals Limited | `RAJSREESUG.NS` |
| 1977 | `RAJTV` | Raj Television Network Limited | `RAJTV.NS` |
| 1978 | `RALLIS` | Rallis India Limited | `RALLIS.NS` |
| 1979 | `RAMANEWS` | Shree Rama Newsprint Limited | `RAMANEWS.NS` |
| 1980 | `RAMAPHO` | Rama Phosphates Limited | `RAMAPHO.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream ARHAM 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1951-1980-Historical-Data/main/ARHAM/1m/2026/10/ARHAM_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
