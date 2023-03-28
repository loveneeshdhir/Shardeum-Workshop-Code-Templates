# Prerequisites

1. You need to have node.js, npm and yarn installed on your device.
2. To download them, head over to https://nodejs.org
3. After Installing, make sure you have node, type node -v in your terminal/command prompt.
4. Type npm -v to check you have npm.
5. To install yarn, type npm install yarn in your terminal/Command line.

## Setting up the Development Environment

1. In your terminal/Command line, clone the repository using the git clone command
2. cd into the ui folder and then type yarn install -> This will install all required packages to run the frontend.
3. Open the .env file in the ui folder and add the deployed contract address for the Election.sol contract. ```NEXT_PUBLIC_CONTRACT_ADDRESS=<YOUR_CONTRACT_ADDRESS_HERE>```.
4. In the ui directory, run the command, yarn dev. This will open the dapp on your localhost.
5. Visit http://localhost:3000

## Understanding the Code

### Contracts: Election.sol

- A smart contract that creates an election system with candidates and allows users to cast their votes for a particular candidate.

- We define a Candidate struct that has an id, name, and voteCount. The voteCount stores the number of votes received by a candidate.

- We also define an event called VoteCasted that is emitted when a user casts their vote for a candidate. The event logs the address of the user and the candidate they voted for.

- We are using two mappings to store the candidates and the votes. The candidates mapping stores each candidate with their id as the key, while the votes mapping stores the number of votes for each candidate with their id as the key.

- We have a candidatesCount variable that stores the total number of candidates added to the system.

- The constructor function adds two candidates to the system with default names "Candidate 1" and "Candidate 2". The addCandidate function is private and is called by the constructor to add each candidate to the candidates mapping with a unique id and a voteCount of 0.

- The casteVote function takes a candidate id as a parameter and increases their voteCount by 1. It then emits the VoteCasted event with the address of the user who cast the vote and the candidate they voted for.

- The getVotes function takes a candidate id as a parameter and returns the voteCount of the candidate with that id.
