# Live-network-connected-ZK-SNARK-Project
## ZK SNARK DESIGN DESCRIPTION
This project implements a logical gate circuit using the circom programming language. The circuit implements the following truth table:
![image](https://github.com/Infini9te/Live-network-connected-ZK-SNARK-Project/assets/95559909/9afdb6de-f221-4604-80fa-d0e428f34fc2)

## GETTING STARTED
### INSTALLING
1. clone the repository: https://github.com/gmchad/zardkat
2. Open on VS code.

### Executing program
1. Run npm i command.
2. Make the given changes in circuit.circom file
   template Multiplier2 () {  
    signal input a;
    signal input b;

    signal x;

    signal output y;

    component andGate = AND();
    component notGate = NOT();

    andGate.a <== a;
    andGate.b <== b;
    x <== andGate.out;

    notGate.in <== x;
    y <== notGate.out;
    

    
}
template AND() {
    signal input a;
    signal input b;
    signal output out;

    out <== a*b;
}
template NOT() {
    signal input in;
    signal output out;

    out <== 1 + in - 2*in;
}


component main = Multiplier2();

3. Fill in the network in hardhat.config.ts file.

4. Make required env file.

5. Run in following commands:
   npx hardhat circom
   npx hardhat compile
   npx hardhat run scripts/deploy.ts --network mumbai

6. Connect mumbai testnet to metamask.
7. The deployed ID pasted in polygonscan verifies all the transactions.

## AUTHOR
### SHUBHAM

