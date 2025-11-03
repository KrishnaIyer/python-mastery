.PHONY: init

init:
	@echo "Initialize project"
	uv sync
	@echo "Warming up mypy cache..."
	uv run mypy . || true

.PHONY: code.quality

py.quality:
	uv run ruff check
	uv run mypy .

py.test:
	uv run pytest -q
	uv run coverage run -m pytest