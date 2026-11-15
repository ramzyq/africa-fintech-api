# Mergio snapshot: Africa Fintech API

This is a **frozen copy** of [Raphasha27/africa-fintech-api](https://github.com/Raphasha27/africa-fintech-api)
at commit `3a6ddbe`, used for the Mergio **Python track, Level 1**.
It is MIT licensed: the original `LICENSE` and copyright stay in place.

## What Mergio changed

| Change | Why |
| --- | --- |
| Pinned `bcrypt==4.0.1` and added `email-validator` | The original install crashed every test |
| Added `requirements-dev.txt` | One command installs everything needed to run tests |
| Replaced the GitHub workflows with `mergio-check.yml` | One simple check: the test suite on every PR |
| Skipped `test_create_wallet_success` | The API has no way to close a wallet yet, so the test cannot pass |

Nothing in `app/` was changed.

## Run it

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements-dev.txt
pytest -q                        # starting state: 3 failed, 34 passed, 1 skipped
uvicorn app.main:app --reload    # API docs at http://localhost:8000/docs
```

The 3 failing tests are the first Mergio tasks. Don't fix them all at once.
Open the task on Mergio and do them one at a time.
