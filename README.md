# Check a photo of math work

Upload a picture of written math. The Flask app sends it to the Mathpix text API (`https://api.mathpix.com/v3/text`). If Mathpix returns no `text` field, the page responds `Unable to read image :( maybe try different file format?` Otherwise it compares the steps. A problem with an `x` is checked with SymPy. A numeric problem is checked with `eval`. If those disagree, it asks `gpt-4` what went wrong. If there is only one expression, it returns `Seems like this is only the given problem (or there's something wrong on my end).`

## Run the checker

Create `config.py` (it is not in the repo) with `APP_ID`, `APP_KEY` (Mathpix), and `OPENAI_API_KEY`.

```bash
pip install flask requests sympy openai
python app.py
```

Open the Flask debug server and upload an image.

## License

[MIT](LICENSE)
