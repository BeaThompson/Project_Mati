Step 1: Install PySigma + Splunk Backend
First, install PySigma and the Splunk backend directly with pip.

{
pip install sigma pysigma-backend-splunk
}

This pulls the core Sigma parsing engine and the Splunk translation backend.

Step 2: Example PySigma Usage
Here’s a quick Python one-liner to convert a Sigma YAML rule to a Splunk SPL query:

{
  from sigma.collection import SigmaCollection
  from sigma.backends.splunk import SplunkBackend

  rule = SigmaCollection.from_yaml(open('./rules/windows/suspicious_powershell.yml'))
  backend = SplunkBackend()
  queries = rule.translate(backend)
  print(queries)
}

==================================================
Step 3: Automation Script
Built a Python script to automate converting an entire directory of Sigma rules to Splunk SPL.

{
import os
from sigma.collection import SigmaCollection
from sigma.backends.splunk import SplunkBackend

RULES_DIR = './rules'
OUTPUT_DIR = './converted_rules'

os.makedirs(OUTPUT_DIR, exist_ok=True)

backend = SplunkBackend()

for root, dirs, files in os.walk(RULES_DIR):
    for file in files:
        if file.endswith('.yml') or file.endswith('.yaml'):
            rule_path = os.path.join(root, file)
            with open(rule_path, 'r') as f:
                collection = SigmaCollection.from_yaml(f)
                queries = collection.translate(backend)
                base_filename = os.path.splitext(file)[0]
                output_file = os.path.join(OUTPUT_DIR, f'{base_filename}.spl')
                with open(output_file, 'w') as out_f:
                    for query in queries:
                        out_f.write(query + '\n')
                print(f'Converted: {file} -> {output_file}')
}

==================================================
Step 4: Usage Instructions
Place Sigma rules in the rules/ directory.

Run the script.

All converted .spl files will be written to converted_rules/.

Step 5: Bonus Tip
Version control your conversion script and maintain consistent backend options for translation. If you change SIEMs, just swap the backend class.
