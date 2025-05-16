
# Leviathan API

Leviathan is a powerful asynchronous stock and financial data API built with FastAPI. It integrates multiple data sources to provide essential financial metrics and company information.

## Features

- Real-time and historical stock prices
- Financial ratios (PE, PB, etc.)
- Insider trades and corporate actions
- IPO information and upcoming financial events
- Full financial statements (income, cash flow, balance sheet)
- Key ratios and share statistics
- Modular design for scalable integration

---

##  Endpoints Overview

### 📊 Stock Endpoints `/api/v1/stock`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Basic welcome message |
| GET | `/total-shares` | Get total outstanding shares |
| GET | `/pe-ratio` | Get Price-to-Earnings ratio |
| GET | `/price-book-ratio` | Get Price-to-Book ratio |
| GET | `/price` | Get current (delayed) stock price |
| GET | `/insider-trades` | Retrieve insider trading activity |
| GET | `/corporate-actions` | Retrieve corporate events (dividends, splits, etc.) |
| GET | `/capital-increase` | Details about capital increases |
| GET | `/ipos` | Recent and upcoming IPOs |
| GET | `/upcoming-events` | General upcoming financial events |
| GET | `/quote` | Latest stock quote |
| GET | `/historical-prices` | Historical pricing data |
| GET | `/key-ratios` | Financial ratios over time |
| GET | `/share-stats` | Share structure and volume stats |
| GET | `/company-profile` | Overview of company profile |

###  Financial Endpoints `/api/v1/financials`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Basic welcome message |
| GET | `/all` | All financial statements |
| GET | `/balance-sheets` | Historical balance sheets |
| GET | `/cash-flow` | Cash flow statements |
| GET | `/income-statement` | Income statements |

---

### Usage
### Base URL
```
https://leviathan-uchb.onrender.com
```

### Example Request

```bash
curl "https://your-api.com/api/v1/stock/price?exchange=EGX&symbol=SWDY"
```

Response:

```json
{
  "exchange": "EGX",
  "symbol": "SWDY",
  "response": {
    "stockPrice": 79.89
  },
  "date": "2025-05-16T21:21:53.066762"
}
```
### Swagger UI and Docs

https://leviathan-uchb.onrender.com/docs

---
<h2>Supported Exchanges</h2>
<p>The following table shows the available worldwide exchanges with their corresponding time delays (for quotes), locations, and market identifier codes.</p>
<div style="overflow-x: auto; max-width: 100%;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Location</th>
      <th>Market Identifier Code</th>
      <th>Exchange</th>
      <th>Delay in Quotes (in Minutes)</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>United States</td><td>AMEX</td><td>NYSE American</td><td>15</td></tr>
    <tr><td>United States</td><td>XNAS</td><td>Nasdaq Stock Market (Last Sale Price)</td><td>Real-time</td></tr>
    <tr><td>United States</td><td>XNYS</td><td>New York Stock Exchange</td><td>15</td></tr>
    <tr><td>United States</td><td>ARCX</td><td>NYSE ARCA</td><td>15</td></tr>
    <tr><td>United States</td><td>OTCM</td><td>OTCM</td><td>15</td></tr>
    <tr><td>United States</td><td>XOTC</td><td>OTCBB</td><td>15</td></tr>
    <tr><td>United States</td><td>N/A</td><td>Nasdaq Global Indices</td><td>Real-time</td></tr>
    <tr><td>United States</td><td>N/A</td><td>Dow Jones Indices</td><td>Real-time</td></tr>
    <tr><td>United States</td><td>N/A</td><td>S&amp;P Indices</td><td>10</td></tr>
    <tr><td>United States</td><td>N/A</td><td>CME S&amp;P Indices</td><td>10</td></tr>
    <tr><td>United States</td><td>XCME</td><td>Chicago Mercantile Exchange</td><td>10</td></tr>
    <tr><td>United States</td><td>NYMS</td><td>New York Mercantile Exchange</td><td>10</td></tr>
    <tr><td>United States</td><td>CECS</td><td>Commodity Exchange (COMEX)</td><td>10</td></tr>
    <tr><td>United States</td><td>N/A</td><td>Options Price Reporting Authority (OPRA)</td><td>15</td></tr>
    <tr><td>Argentina</td><td>XBUE</td><td>Bolsa de Comercio de Buenos Aires</td><td>20</td></tr>
    <tr><td>Australia</td><td>XASX</td><td>Australian Securities Exchange</td><td>20</td></tr>
    <tr><td>Australia</td><td>N/A</td><td>S&amp;P ASX Indices</td><td>Real-time</td></tr>
    <tr><td>Austria</td><td>XWBO</td><td>Wiener Boerse AG</td><td>15</td></tr>
    <tr><td>Belgium</td><td>XBRU</td><td>Euronext Brussels</td><td>15</td></tr>
    <tr><td>Brazil</td><td>BVMF</td><td>B3 - Brazil Stock Exchange</td><td>15</td></tr>
    <tr><td>Canada</td><td>XCNQ</td><td>Canadian National Stock Exchange</td><td>15</td></tr>
    <tr><td>Canada</td><td>XTSE</td><td>Toronto Stock Exchange</td><td>15</td></tr>
    <tr><td>Canada</td><td>XTSX</td><td>TSX Venture Exchange</td><td>15</td></tr>
    <tr><td>Chile</td><td>XSGO</td><td>Santiago Stock Exchange</td><td>20</td></tr>
    <tr><td>China</td><td>XSHG</td><td>Shanghai Stock Exchange</td><td>15</td></tr>
    <tr><td>China</td><td>XSHE</td><td>Shenzhen Stock Exchange</td><td>15</td></tr>
    <tr><td>Columbia</td><td>XBOG</td><td>Bolsa de Valores de Colombia</td><td>End of Day</td></tr>
    <tr><td>Cyprus</td><td>XCYS</td><td>Cyprus Stock Exchange</td><td>15</td></tr>
    <tr><td>Denmark</td><td>XCSE</td><td>Nasdaq Copenhagen</td><td>15</td></tr>
    <tr><td>Egypt</td><td>XCAI</td><td>Egyptian Exchange</td><td>15</td></tr>
    <tr><td>Estonia</td><td>XTAL</td><td>Nasdaq Tallinn</td><td>15</td></tr>
    <tr><td>Finland</td><td>XHEL</td><td>Nasdaq Helsinki</td><td>15</td></tr>
    <tr><td>France</td><td>XPAR</td><td>Euronext Paris</td><td>15</td></tr>
    <tr><td>Germany</td><td>XFRA</td><td>Deutsche Boerse AG</td><td>15</td></tr>
    <tr><td>Germany</td><td>XETR</td><td>Xetra</td><td>15</td></tr>
    <tr><td>Greece</td><td>XATH</td><td>Athens Exchange</td><td>15</td></tr>
    <tr><td>Hong Kong</td><td>XHKG</td><td>Hong Kong Stock Exchange</td><td>15</td></tr>
    <tr><td>Iceland</td><td>XICE</td><td>Nasdaq Iceland</td><td>15</td></tr>
    <tr><td>India</td><td>XBOM</td><td>Bombay Stock Exchange</td><td>15</td></tr>
    <tr><td>India</td><td>XNSE</td><td>National Stock Exchange of India</td><td>5 minute snapshot</td></tr>
    <tr><td>Indonesia</td><td>XIDX</td><td>Indonesia Stock Exchange</td><td>End of Day</td></tr>
    <tr><td>Ireland</td><td>XDUB</td><td>Euronext Dublin</td><td>15</td></tr>
    <tr><td>Israel</td><td>XTAE</td><td>Tel Aviv Stock Exchange</td><td>End of Day</td></tr>
    <tr><td>Italy</td><td>XMIL</td><td>Borsa Italiana</td><td>15</td></tr>
    <tr><td>Japan</td><td>XTKS</td><td>Tokyo Stock Exchange</td><td>20</td></tr>
    <tr><td>Korea</td><td>XKRX</td><td>Korea Stock Exchange</td><td>20</td></tr>
    <tr><td>Latvia</td><td>XRIS</td><td>Nasdaq Riga</td><td>15</td></tr>
    <tr><td>Lithuania</td><td>XLIN</td><td>Nasdaq Vilnius</td><td>15</td></tr>
    <tr><td>Malaysia</td><td>XKLS</td><td>Bursa Malaysia</td><td>15</td></tr>
    <tr><td>Malaysia</td><td>N/A</td><td>FTSE Bursa Malaysia Indices</td><td>15</td></tr>
    <tr><td>Mexico</td><td>XMEX</td><td>Mexican Stock Exchange</td><td>20</td></tr>
    <tr><td>New Zealand</td><td>XNZE</td><td>New Zealand Stock Exchange</td><td>20</td></tr>
    <tr><td>Norway</td><td>XOSL</td><td>Oslo Bors Asa</td><td>15</td></tr>
    <tr><td>Peru</td><td>XLIM</td><td>Bolsa de Valores de Lima</td><td>End of Day</td></tr>
    <tr><td>Philippines</td><td>XPHS</td><td>Philippine Stock Exchange</td><td>15</td></tr>
    <tr><td>Poland</td><td>XWAR</td><td>Warsaw Stock Exchange</td><td>15</td></tr>
    <tr><td>Portugal</td><td>XLIS</td><td>Euronext Lisbon</td><td>15</td></tr>
    <tr><td>Romania</td><td>XBSE</td><td>Bucharest Stock Exchange</td><td>15</td></tr>
    <tr><td>Russia</td><td>MISX</td><td>Moscow Exchange</td><td>15</td></tr>
    <tr><td>Saudi Arabia</td><td>XSAU</td><td>Saudi Stock Exchange</td><td>15</td></tr>
    <tr><td>Singapore</td><td>XSES</td><td>Singapore Exchange</td><td>10</td></tr>
    <tr><td>South Africa</td><td>XJSE</td><td>Johannesburg Stock Exchange</td><td>15</td></tr>
    <tr><td>South Africa</td><td>N/A</td><td>FTSE JSE Indices</td><td>15</td></tr>
    <tr><td>Spain</td><td>BMEX</td><td>Bolsas y Mercados Espanoles</td><td>15</td></tr>
    <tr><td>Sweden</td><td>XSTO</td><td>Nasdaq Stockholm</td><td>15</td></tr>
    <tr><td>Switzerland</td><td>XSWX</td><td>Swiss Exchange</td><td>15</td></tr>
    <tr><td>Taiwan</td><td>XTAI</td><td>Taiwan Stock Exchange</td><td>20</td></tr>
    <tr><td>Thailand</td><td>XBKK</td><td>Stock Exchange of Thailand</td><td>15</td></tr>
    <tr><td>The Netherlands</td><td>XAMS</td><td>Euronext Amsterdam</td><td>15</td></tr>
    <tr><td>Turkey</td><td>XIST</td><td>Borsa Istanbul</td><td>End of Day</td></tr>
    <tr><td>Ukraine</td><td>XUAX</td><td>Ukrainian Stock Exchange</td><td>End of Day</td></tr>
    <tr><td>United Arab Emirates</td><td>XADS</td><td>Abu Dhabi Securities Exchange</td><td>15</td></tr>
    <tr><td>United Arab Emirates</td><td>XDFM</td><td>Dubai Financial Market</td><td>15</td></tr>
    <tr><td>United Kingdom</td><td>XLON</td><td>London Stock Exchange</td><td>15</td></tr>
    <tr><td>United Kingdom</td><td>N/A</td><td>FTSE International</td><td>15</td></tr>
    <tr><td>Venezuela</td><td>BVCA</td><td>Caracas Stock Exchange</td><td>End of Day</td></tr>
    <tr><td>Vietnam</td><td>XSTC</td><td>Hochiminh Stock Exchange</td><td>15</td></tr>
  </tbody>
</table>
</div>


##  Tech Stack

- FastAPI
- aiohttp
- Pydantic

---

##  Coming Soon

- Source file - Leviathan will go open source in 2026.

---

##  Author

**Leviathan API** by Ahmed Ramadan  

Connect on [LinkedIn](https://www.linkedin.com/in/theahmedrmdan/)

If you have any questions or feedback, feel free to email me TheAhmedRmdan@gmail.com
