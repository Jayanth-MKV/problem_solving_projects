# AI Research Playbooks

Small, executable playbooks for exploring relational data with pandas and PostgreSQL. The current repository focuses on deterministic query techniques; it does not yet contain an LLM or text-to-SQL integration.

## What is included

| Playbook | What it demonstrates | Runtime |
| --- | --- | --- |
| `p-1` | Case-insensitive filtering across related in-memory tables, with matching records propagated through their relationships | Python + pandas |
| `p-2` | Parameterized PostgreSQL queries, CTEs, and pivoting entity-attribute-value tables into analysis-friendly results | Python + PostgreSQL |

The sample output images inside each phase show the tables and query results produced by the scripts.

## Quick start

Run the self-contained pandas example:

```bash
git clone https://github.com/jayanth-mkv/ai-research-playbooks.git
cd ai-research-playbooks/text-to-sql-project-llm-python-dataevaluation/p-1
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install pandas
python main.py
```

The PostgreSQL phase also requires `psycopg2` and a populated local database. Review the loader scripts and replace the example connection values before running it:

```bash
cd ../p-2
pip install pandas psycopg2-binary
python main.py
```

## Repository map

```text
text-to-sql-project-llm-python-dataevaluation/
├── p-1/   # in-memory relational filtering
└── p-2/   # PostgreSQL loading and querying
```

## Current scope

- The data and database credentials in the scripts are local examples, not production configuration.
- Dependencies are not pinned, so reproduce the environment explicitly for long-lived experiments.
- The repository name describes the broader research direction; natural-language query generation is not implemented yet.

## Next steps

- Move database settings to environment variables.
- Add a reproducible schema and seed-data script for the PostgreSQL phase.
- Add tests before using these query builders with real data.
