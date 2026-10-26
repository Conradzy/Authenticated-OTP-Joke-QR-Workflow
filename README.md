# Authenticated OTP-Protected Joke QR Workflow

Adds an explicit authenticated session gate to a SQLite and TOTP notebook. Joke retrieval and QR-code generation are permitted only after a successful username, password, and Google Authenticator code check.

## Workflow

1. Install the QR and TOTP packages in Colab.
2. Create the SQLite user table and a demo account.
3. Generate and scan an Authenticator provisioning QR code.
4. Set session authentication state after a successful three-factor input check.
5. Protect Joke API and joke-to-QR operations behind that state.

## Data Requirements

- No external dataset is required; `users.db` is created at runtime.
- The notebook calls the Official Joke API.

Datasets and generated artifacts are not included unless they are embedded directly in the notebook.

## Requirements

- pyotp
- qrcode
- Pillow
- requests
- SQLite (Python standard library)
- IPython

Install missing packages in your Jupyter or Google Colab environment before running the notebook.

## Running the Notebook

1. Open [`LoginOTPSQLite_QRCode_API_Final_WITH_LOGIN.ipynb`](LoginOTPSQLite_QRCode_API_Final_WITH_LOGIN.ipynb) in Jupyter Notebook or Google Colab.
2. Place any required data files in the path expected by the notebook.
3. Update local or Google Drive paths where needed.
4. Run the cells from top to bottom.

## Outputs

- Runtime SQLite database
- Authenticator QR image
- Authenticated joke QR image

## Security and Responsible Use

For teaching only: passwords are stored in plaintext and authentication state exists only in the notebook runtime. Embedded outputs were cleared in the public copy to avoid exposing enrollment secrets.

## Repository Contents

```text
.
|-- README.md
`-- LoginOTPSQLite_QRCode_API_Final_WITH_LOGIN.ipynb
```

## Notes

- This repository preserves the analysis as a notebook-first educational project.
- Results may vary with dataset versions, random splits, package versions, and available hardware.
- Review file paths and runtime-specific commands before executing outside Google Colab.
