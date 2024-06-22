# ETH-AVAX
The OwnershipContract is a simple Ethereum smart contract designed to manage ownership. It allows only the designated owner to perform specific actions, providing mechanisms to check if the caller is the owner through different Solidity control structures. This contract is intended for educational purposes to demonstrate ownership checks using require, revert, and assert.

Contract Details
Pragma Directive
solidity

pragma solidity >=0.6.12 <0.9.0;
Specifies the Solidity compiler version range compatible with this contract. It ensures the contract is compiled with a version between 0.6.12 and 0.9.0.
State Variable
solidity

address public owner;
Declares a public state variable owner of type address. This variable stores the address of the contract owner and is publicly accessible.
Constructor
solidity

constructor() {
    owner = msg.sender;
}
The constructor is executed once when the contract is deployed. It sets the owner variable to the address of the account that deployed the contract (msg.sender).
Functions
onlyOwner
solidity

function onlyOwner() public view {
    require(msg.sender == owner, "Only the owner can call this function.");
}
A public view function that checks if the caller is the owner using the require statement. If the caller is not the owner, it reverts with an error message "Only the owner can call this function."
onwerHere
solidity

function onwerHere() public view {
    if(msg.sender != owner){
        revert("The caller is not the owner.");
    }
}
A public view function that checks if the caller is the owner using an if statement and the revert function. If the caller is not the owner, it reverts with an error message "The caller is not the owner."
Owner
solidity

function Owner() public view {
    assert(msg.sender == owner);
}
A public view function that checks if the caller is the owner using the assert statement. If the caller is not the owner, it throws an error. assert is generally used to test for internal errors and invariants.
Usage
Deploy the OwnershipContract.
The deployer of the contract becomes the owner.
Call onlyOwner, onwerHere, or Owner functions to verify ownership. Each function uses a different control structure to enforce the ownership check.
Conclusion
The OwnershipContract demonstrates basic ownership functionality in Solidity using three different mechanisms to enforce that only the owner can perform certain actions. This contract is useful for understanding how to implement and enforce ownership restrictions in Ethereum smart contracts.
