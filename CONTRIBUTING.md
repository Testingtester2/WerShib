# Contributing to SHIB Accepted

Want to add a merchant that accepts SHIB? Just edit one file and open a pull request!

## Adding a New Merchant

1. **Fork** this repository
2. **Edit** `merchants.json`
3. **Add** your merchant entry to the array
4. **Open** a pull request

### Merchant Entry Format

Add a new object to the `merchants.json` array:

```json
{
  "name": "Store Name",
  "url": "https://www.example.com",
  "category": "retail",
  "icon": "🛒",
  "description": "Short description of how SHIB is accepted here.",
  "methods": ["bp"]
}
```

#### Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Merchant display name |
| `url` | Yes | Full URL including `https://` |
| `category` | Yes | One of the categories below |
| `icon` | Yes | Single emoji representing the merchant |
| `description` | Yes | Brief description (under 100 chars) |
| `methods` | Yes | Array of payment method codes (see below) |
| `badge` | No | Optional highlight badge text (e.g. `"NEW"`) |

#### Categories

| Code | Label |
|------|-------|
| `flexa` | Flexa Network (in-store) |
| `luxury` | Luxury & Fashion |
| `retail` | Retail & Shopping |
| `entertainment` | Film, TV & Gaming |
| `food` | Food & Dining |
| `travel` | Travel & Hotels |
| `sports` | Sports & Teams |
| `crypto` | Crypto Services |
| `tech` | Tech & Hosting |
| `auto` | Auto & Vehicles |
| `charity` | Charity & Donations |

#### Payment Methods

| Code | Label | Meaning |
|------|-------|---------|
| `fl` | Flexa | Accepted via Flexa network |
| `bp` | BitPay | Accepted via BitPay |
| `di` | Direct | Direct SHIB wallet payment |
| `np` | NOWPay | Via NOWPayments gateway |
| `cg` | CoinGate | Via CoinGate gateway |

### Example

```json
{
  "name": "Cool Store",
  "url": "https://www.coolstore.com",
  "category": "retail",
  "icon": "😎",
  "description": "Awesome products. Pay with SHIB via BitPay.",
  "methods": ["bp"],
  "badge": "NEW"
}
```

## Guidelines

- Only add merchants that **currently accept SHIB** (verify before submitting)
- Provide accurate URLs (must be `https://`)
- Keep descriptions concise and factual
- One merchant per entry (don't combine multiple stores)
- Place new entries at the end of the JSON array
- Make sure your JSON is valid (no trailing commas!)

## Testing Locally

Open `index.html` in a browser with a local server:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Then visit `http://localhost:8000` to verify your merchant appears correctly.

## Questions?

Open an issue if you're unsure about anything!
