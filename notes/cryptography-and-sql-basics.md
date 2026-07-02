# Notes: Cryptography Concepts & SQL Basics

Condensed reference notes from TryHackMe's Cryptography Concepts and
Database/SQL Basics rooms. Kept as reference material rather than full
writeups since these are conceptual foundations rather than hands-on
attack chains.

## Cryptography Concepts

**Encoding vs Encryption vs Hashing** (common interview question):
- **Encoding** — reversible transformation for compatibility (Base64, URL
  encoding). Not secure — no key required to reverse it.
- **Encryption** — reversible transformation requiring a key (AES, RSA).
  Confidentiality-focused.
- **Hashing** — one-way transformation (MD5, SHA-256). Used for integrity
  checks and password storage, not confidentiality.

**Symmetric vs Asymmetric encryption:**
- Symmetric: same key for encrypt/decrypt (AES) — fast, used for bulk data
- Asymmetric: public/private key pair (RSA) — slower, used for key exchange
  and digital signatures

**Why it matters for security work:** identifying weak hashing (e.g. MD5
for password storage) is a common finding in both pentests and SOC
investigations.

## Database & SQL Basics

Core query structure:
```sql
SELECT column_name FROM table_name WHERE condition;
```

Key concepts covered:
- Tables, rows, columns, primary/foreign keys
- Basic CRUD operations (`SELECT`, `INSERT`, `UPDATE`, `DELETE`)
- `JOIN` types (INNER, LEFT, RIGHT) for combining table data

**Why it matters for security work:** understanding legitimate query
structure is the prerequisite for recognizing and constructing SQL
injection payloads — this connects directly to the SQL Injection room in
the pentesting track.
