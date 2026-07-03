# Contributing

Thanks for your interest in improving **LlamaIndex RAG Examples**! Contributions of all
kinds are welcome — bug reports, documentation fixes, and new examples.

## Ways to contribute

- **Report a bug** — open an issue describing what you expected, what happened, and the
  steps to reproduce it.
- **Suggest an improvement** — open an issue outlining the idea before starting large
  changes.
- **Submit a pull request** — for fixes and small enhancements.

## Development workflow

1. Fork the repository and create a feature branch:

   ```bash
   git checkout -b my-improvement
   ```

2. Set up the environment for the example you are working on (see its `README.md`).

3. Make your changes. For notebooks, please **clear all cell outputs** before committing
   to keep diffs readable:

   ```bash
   jupyter nbconvert --clear-output --inplace "path/to/main.ipynb"
   ```

4. Never commit secrets. API keys belong in a local `.env` file (ignored by git); update
   the `.env.example` template instead when adding a new key.

5. Commit with a clear message and open a pull request describing your change.

## Code style

- Keep notebook cells focused and well-commented.
- Prefer small, reviewable pull requests.
- Update the relevant `README.md` when you change setup steps or dependencies.

By contributing, you agree that your contributions will be licensed under the
[MIT License](./LICENSE).
