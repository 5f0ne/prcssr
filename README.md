# Description

Command Execution with Logging

# Disclaimer

- No sanitization is applied by prcssr
- You are responsible to sanitize the input

# Installation

`pip install prcssr`

# Usage

**From command line:**

`python -m prcssr -c CMD [-l LOG]`

| Option | Short | Type | Default | Description |
|---|---|---|---|---|
|--cmd | -c | String | - | The command |
|--log | -l | String | prcssr.log | Path to log file |

**Programmatically:**

```python
from prcssr.model.Processor import Processor

p = Processor("info.log")

p.process("type test.txt")

stdout = p.processGetStdOut("type test.txt")

for line in stdout.readlines():
    print(line)
```


# Example

`python -m prccsr -c "type test.txt" -l info.log`

Creates `info.log` with the following content:

```
[1970-01-01 10:10:10,214] | INFO | prcssr started!
[1970-01-01 10:10:10,217] | INFO | ----------
[1970-01-01 10:10:10,219] | INFO | CMD: type .\LICENSE.md
[1970-01-01 10:10:10,224] | INFO | ----------
[1970-01-01 10:10:10,230] | INFO | # This is a test file for prccsr
[1970-01-01 10:10:10,241] | INFO | ----------
```


# License

MIT