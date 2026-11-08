# Syntax Validation Rule

Whenever modifying or creating YAML (`.yml`, `.yaml`) or JSON (`.json`) files (including GitHub workflows in `.github/workflows/`, dependabot configuration, quadlets, or plugin configurations):
- **Always validate syntax with a parser before completing changes.**
- For YAML files: Run `ruby -e 'require "yaml"; Dir.glob(".github/**/*.yml").each { |f| YAML.load_file(f) }'` (or parse the modified YAML file).
- For JSON files: Run `python3 -m json.tool <file> > /dev/null` (or parse the modified JSON file).
- Never commit or leave merge conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
