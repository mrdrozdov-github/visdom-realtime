# Visdom Realtime

This project contains two scripts that enable Visdom updates in realtime.

### Part 1: Metrics Writer.

Use this in your experiments to write relevant metrics to file that would populate visdom graphs.

### Part 2: Reporter.

Run this while you run experiments so that your metrics are written to visdom in realtime.

# More details below...

### Metrics Writer

Simple writes a sequence of (float, int) pairs to file. Look at `test.py` for usage.

### Reporter

A crude but effective metrics digest. Works with Visdom.

Depends on:

- numpy
- python-gflags
- visdom
- watchdog

Example Usage:

    $ python -m visdom.server # in a separate terminal
    $ python reporter.py \
        --state ./runs/.visdom_state.json \ # keeps state for the reporter
        --root ./runs \                     # crawls directory for experiments and metric files
        --suffix .metric \                  # file extension indicating a metric file
        --verbose
