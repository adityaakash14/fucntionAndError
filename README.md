// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract myContract {
    uint256 public value;

    function setValue(uint256 _newValue) public {
        // Using require() to validate inputs
        require(_newValue > 0, "Value must be greater than 0");
        
        value = _newValue;
    }

    function assertExample(uint256 _a, uint256 _b) public pure returns (uint256) {
        // Using assert() for internal consistency checks
        assert(_a != _b);
        
        return _a + _b;
    }

    function revertExample() public pure {
        // Using revert() to intentionally trigger a revert
        revert("This function always reverts");
    }
}
