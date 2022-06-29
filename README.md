# Distortion
The contract for the Distortion airdrop.


Site: https://0xdistortion.com


# Important Functions

- airdrop(address[] memory _to, uint256[][] memory _tokenIds)
  - Airdrop specific tokens to specific addresses.
  - Proper token IDs owned by specific users can be taken from a snapshot on a certain block.


- disableAirdrop()
  - Disables the airdrop function forever.
  - Must be used after all tokens were airdropped.


# Generative Art Functions

- generateNum()/generateNumUint()
  - Generates an arbitry number (string/uint) based on an input with uint(keccak256(...))

- genDefs()
  - Generates the SVG definitions which include xy frequencies and scale for the Distortion piece.

- getFrequency()
  - Calculates the display frequency which is the product of the x and the y frequencies (for metadata display).

- genMiddle()/genSquares()/genEnd()
  - Generates the middle, end and squares of the art piece.
  - Sets the specific color.

- generateDistortion()
  - Puts everything together and is called inside the tokenURI() function.


- withdraw() - simple withdraw to owner() address if there is a price to the mint (likely not)
```
function withdraw() public onlyOwner {
            uint256 balance = address(this).balance;
            Address.sendValue(payable(owner()), balance);
    }
```
