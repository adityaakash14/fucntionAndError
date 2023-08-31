// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AssertionExample {
    uint256 public value;

    function setValue(uint256 _newValue) external {
        // Use require() to check conditions and revert if they're not met
        require(_newValue > value, "New value must be greater than the current value");
        
        value = _newValue;
    }

    function assertExample(uint256 _input) external pure returns (uint256) {
        // Use assert() to check for invariants and revert if they're violated
        uint256 result = _input * 2;
        assert(result > _input);
        
        return result;
    }

    function revertExample(uint256 _input) external pure returns (uint256) {
        // Use revert() to explicitly revert the transaction with a custom message
        if (_input == 0) {
            revert("Input cannot be zero");
        }
        
        return 100 / _input;
    }
}
