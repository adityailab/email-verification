# 📧 Email Validator App (Streamlit)

This project is a Python-based Streamlit web app for validating email addresses individually or in bulk. It performs checks for proper formatting, DNS records, MX records, and can optionally validate emails via SMTP probing to determine deliverability.

---

## 🚀 Features

- ✅ Validate a single email or bulk email list
- 🧪 Checks:
  - Regex format
  - DNS records (A, NS, CNAME)
  - MX records (for receiving mail)
  - Optional SMTP probing (for mailbox verification)
- 📄 Accepts `.csv` and `.xlsx` files for bulk validation
- 🎨 Outputs a downloadable Excel file with color-coded results
- 🖥️ Simple and clean Streamlit user interface

---

## 📸 Screenshots

### Streamlit App - File Upload Interface
![Streamlit Upload Interface](screenshot1.png)

### Validation Output in Excel (Color-coded)
![Excel Validation Output](screenshot2.png)

### Streamlit - Post-validation Download Option
![Streamlit Result Download](screenshot3.png)

---

## 📂 Input Format

### 📧 Single Email

- Enter any email directly into the input field.

### 📁 Bulk File Upload

- Upload a `.csv`, `.xlsx`, or `.xls` file.
- Required column name: **`Email address`**

**Example:**

| Email address         |
|-----------------------|
| test@example.com      |
| invalid@domain        |
| hello@company.org     |

---

## 🎨 Output

- Excel file with:
  - `Validation Status`: Valid / Invalid / Likely Invalid
  - `Validation Message`: Describes the result
- Cell color highlights:
  - 🟢 Green: Valid
  - 🔴 Red: Invalid
  - 🟡 Yellow: Likely Invalid (e.g., SMTP inconclusive)

---

## 🛠️ Setup Instructions

### 1. Clone this Repository

```bash
git clone https://github.com/adityailab/email-verification.git
cd email-verification
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```


---

## ▶️ Run the Application

```bash
streamlit run valid15.py
```

Replace `valid15.py` with your actual file name if different.

---

## 🔎 How It Works

1. **Email Format Check**: Uses regular expressions.
2. **DNS Lookup**: Resolves A, NS, and CNAME records.
3. **MX Lookup**: Checks if domain has mail servers.
4. **SMTP Probing (optional)**: Connects to mail server and sends test handshake to verify the mailbox (RCPT TO).

---

## ⚠️ Important Notes

- SMTP servers (especially Gmail, Yahoo) may throttle or block probes.
- Always use SMTP probing cautiously to avoid being rate-limited.
- Some results may be inconclusive due to mail server configurations.

---

## License

This project is licensed under the MIT License.

---

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- [dnspython](https://www.dnspython.org/)
- [OpenPyXL](https://openpyxl.readthedocs.io/en/stable/)

---

