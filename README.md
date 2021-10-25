# rh promotion panel command simulator

The RH Promotion Panel Command Simulator is solely for the use by a
very specific Red Hat employee during a very specific presentation.
Feel free to modify this code to suit your own needs.

## Setup

```bash
git clone ${repo}

cd ${repo-dir}

chmod +x rh
```

## Running the application

To run commands as `rh` instead of `./rh`, add dir to path:

```bash
export PATH:${pwd}:$PATH
```

You can now use the application as intended:

```bash
rh --help`
```

## Creating your own simulation

Modify the `example.json` file to fit your needs by adding or removing
additional commands as needed.

The structure of objects are as follows:

Single line command example:

```json
"command1": {
    "description": "This is the help description",
    "h": "rh command1",
    "run": ["This is the simulated output"]
}
```

Multi-line command example with overwriting lines:

```json
"command2": {
    "description": "This is another help description",
    "h": "rh command2",
    "run": [
        "Command 2 started...",
        "[INFO] Status update 1",
        "[INFO] Status update 2",
        "[INFO] Status update 3",
        "Command 2 COMPLETE"
    ]
}
```

The simulator uses echo interpretation to allow for special formatting experiences.
For example, here is a multi-line command example with overwriting lines:

```json
"command3": {
    "description": "This is yet another help description",
    "h": "rh command3",
    "run": [
        "Gathering necessary dependencies...",
        "\\e[1A\\e[KGathering necessary dependencies....",
        "\\e[1A\\e[KGathering necessary dependencies.....",
        "\\e[1A\\e[KGathering necessary dependencies.....COMPLETE"
    ]
}
```
