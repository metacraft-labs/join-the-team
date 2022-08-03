# Ethereum 2.0 merkle proof

Create a function that given:

* a consensus-layer `blockHash` (Ethereum 2.0 block)
* a merkle `proof`
* an `account`
* and a `balance`

verifies that the given `account` has the given `balance`

## Pointers

Follow the relationship between the following SSZ types:

* `BeaconBlock`
* `BeaconBlockBody`
* `Eth1Data`

and the following Eth1 data structures:

* Block
* stateRoot
* [Patricia Merkle Trie][patricia-merkle-trie]


## Implementation language

You're free to use the language you're most comfortable using.

## Example function signature

```ts
type HexString = string;
type ByteArray = HexString | Uint8Array;

type Eth2BlockHash = ByteArray;
type Hash = ByteArray;
type MerkleProof = Hash[];
type Eth1AccountInfo = { account: ByteArray; balance: bigint; }

function verifyAccountBalance(
  blockHash: Eth2BlockHash,
  proof: MerkleProof,
  whatToProve: Eth1AccountInfo
): Promise<boolean>;
```

## Resources

* [Simple Serialize (SSZ)][ssz]
* [Ethereum consensus-specs SSZ Merkle Proofs specification][ssz-merkle-proofs]
* [Phase0 Beacon Chain Spec][phase0-beacon-chain]
* [SSZ container types defined in the Phase0 Beacon Chain Spec][becaon-chain-ssz-containers]

[ssz]: https://github.com/ethereum/consensus-specs/blob/dev/ssz/simple-serialize.md
[ssz-merkle-proofs]: https://github.com/ethereum/consensus-specs/blob/dev/ssz/merkle-proofs.md
[phase0-beacon-chain]: https://github.com/ethereum/consensus-specs/blob/dev/specs/phase0/beacon-chain.md
[becaon-chain-ssz-containers]: https://github.com/ethereum/consensus-specs/blob/dev/specs/phase0/beacon-chain.md#containers
[patricia-merkle-trie]: https://ethereum.org/en/developers/docs/data-structures-and-encoding/patricia-merkle-trie
