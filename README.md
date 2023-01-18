# Merkle Tree Gift List 🎁

An application, which gives out gifts, but only to names on the list. The catch is that on the server you are only allowed to store one 32 byte value in the server memory. This 32 byte value has to be enough for the server to be able to determine who is on the list.

## Getting Started

To get started with the repository, clone it and then run `npm install` in the top-level directory to install the depedencies.

There are three folders in this repository:

## Client

You can run the client from the top-level directory with `node client/index`. This file is a script which will send an HTTP request to the server.

Think of the client as the _prover_ here. It needs to prove to the server that some `name` is in the `MERKLE_ROOT` on the server. 

## Server

You can run the server from the top-level directory with `node server/index`. This file is an express server, which will be hosted on port 1225 and respond to the client's request.

Think of the server as the _verifier_ here. It needs to verify that the `name` passed by the client is in the `MERKLE_ROOT`. If it is, then we can send the gift! 

## Utils

There are a few files in utils:

- `niceList.json` contains all the names of the people who deserve a gift this year.
- `MerkleTree.js` contains a basic Merkle tree implementation functions to retrieve the Merkle root and get a Merkle proof.
- `verifyProof.js` a function to prove a name is in the Merkle root.
