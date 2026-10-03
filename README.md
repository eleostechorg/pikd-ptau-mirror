# pikd-ptau-mirror

A mirror of one public file: **`powersOfTau28_hez_final_16.ptau`**, phase 1 of
the Hermez Groth16 trusted-setup ceremony, supporting circuits of up to 2¹⁶
constraints.

It exists because every documented source for this file now returns **403**:
the `zkevm` Google Cloud bucket that snarkjs's own README points to (every ptau
size, with the bucket listing returning 401) and the older Hermez S3 bucket.
Without it, nobody can build the PIKD attestation circuits from a clean clone,
or reproduce their verification keys.

## Do not trust this mirror. Check the digest.

```
sha256  1c401abb57c9ce531370f3015c3e75c0892e0f32b8b1e94ace0f6682d9695922
bytes   75580568
```

The digest is the authority, not the host. It is the same value pinned in
`scripts/fetch-ptau.sh`, and it was pinned *before* the original sources went
dark. A mirror that served different bytes would be refused by that script
and should be refused by you.

```bash
shasum -a 256 powersOfTau28_hez_final_16.ptau
```

## What this file is, and what it is not

It is the output of a multi-party ceremony that PIKD did not run and could not
have subverted alone; its security rests on at least one honest participant
among many, none of them us. Mirroring it adds nothing to that trust and takes
nothing away: the bytes either match the digest or they do not.

It is **not** PIKD's phase-2 setup. That is per-circuit, and at the time of
writing every PIKD key is development-class — see the attestation repository's
`circuits/ceremony/CEREMONY.md`.

## Provenance

Copied from a local copy whose SHA-256 matched the pinned digest on
2026-10-03. The file is published unmodified, as a release asset.
