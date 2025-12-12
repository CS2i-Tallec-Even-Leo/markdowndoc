```yml
name: Demo

on:
  push:
    branches:
      - main
jobs:
  build:
    # Machine
    runs-on: ubuntu-slim

    # Steps
    steps:
      - name: Test 1
        run: echo "This is a demo workflow"
      - name: Test 2
        run: |
          echo "It runs on push to main branch"
          echo "Using ubuntu-slim as the runner"
```
