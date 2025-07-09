# acvp-vectors

ACVP-server (https://github.com/usnistgov/ACVP-Server)
is a great source of test vectors for cryptographic software.
However, it's unnecessarily big, hosting raw JSON files.

The fork optimizes repo size from from 1GB to ~350MB by using gzip compression and
removing unused files.

To reproduce:

    git clone https://github.com/usnistgov/ACVP-Server
    cd ACVP-Server
    rm -rf .github _config docs gen-val/samples gen-val/src
    find gen-val/json-files -iname '*.json' -exec gzip {} \;
