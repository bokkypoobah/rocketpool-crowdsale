# RocketPool Presale And Crowdsale Contracts Audit

## Summary

[Rocket Pool](https://www.rocketpool.net/) intends to run a presale commencing on September 2017, and the crowdsale in October 2017.

Bok Consulting Pty Ltd was commissioned to perform an audit on the crowdsale and token Ethereum smart contract for the upcoming
RocketPool crowdsale.

This audit has been conducted on the RocketPool source code in commits 
[5af99719](https://github.com/darcius/rocketpool-crowdsale/tree/5af997191a939a5a3f9ea38a696da155e53455f6),
[8147b2f2](https://github.com/darcius/rocketpool-crowdsale/tree/8147b2f2f4c535777ab5750240709748dfee0377),
[19372b87](https://github.com/darcius/rocketpool-crowdsale/tree/19372b8736371810ed0e5268281dc7563127a269),
[270c5a09](https://github.com/darcius/rocketpool-crowdsale/tree/270c5a091444ed449d6dcf7cfffb85fabaaae64b),
[4a3d45af](https://github.com/darcius/rocketpool-crowdsale/tree/4a3d45afaf53229ec62cd5003b843ab63d6dddc1),
[aa76189b](https://github.com/darcius/rocketpool-crowdsale/commit/aa76189bf00d8552dd302dba37743717f75eee92),
[6672f7d2](https://github.com/darcius/rocketpool-crowdsale/commit/6672f7d2d552f59b2d35cca16021c21015450917) and
[ddaba0e9](https://github.com/darcius/rocketpool-crowdsale/commit/ddaba0e9f6b02bb150ab6aa2ca8d12af246adb17).

No potential vulnerabilities have been identified in the **RocketPoolPresale** and **RocketPoolToken** contract.

No potential vulnerabilities have been identified in the **RocketPoolCrowdsale** contract.

<br />

### Crowdsale And Token Mainnet Addresses

Token address [0xb4efd85c19999d84251304bda99e90b92300bd93](https://etherscan.io/address/0xb4efd85c19999d84251304bda99e90b92300bd93#code) with
the token explorer [0xb4efd85c19999d84251304bda99e90b92300bd93](https://etherscan.io/token/0xb4efd85c19999d84251304bda99e90b92300bd93) view.

Presale wallet [0x4e3bc0dc25c42ed2745bfc67f1d0daa52103c01a](https://etherscan.io/address/0x4e3bc0dc25c42ed2745bfc67f1d0daa52103c01a#internaltx).

<br />

#### Presale Agent

Presale sale agent [0xB0dEfE01153DFc7fE58c1ad49925B64Fc67fde9e](https://etherscan.io/address/0xB0dEfE01153DFc7fE58c1ad49925B64Fc67fde9e#internaltx).

The tx [0xc50a3778](https://etherscan.io/tx/0xc50a3778b05b919b7559da5803763d5cfe247994796b6c4959eedc48571b5337) links this contract with the token
contract and has the following instruction:

    setSaleAgentContract(address _saleAddress, string _saleContractType,
      uint256 _targetEthMin, uint256 _targetEthMax,
      uint256 _tokensLimit, uint256 _minDeposit, uint256 _maxDeposit,
      uint256 _startBlock, uint256 _endBlock, address _depositAddress)

    MethodID: 0xa7a8add2
    [0]:000000000000000000000000b0defe01153dfc7fe58c1ad49925b64fc67fde9e   _saleAddress: 0xb0defe01153dfc7fe58c1ad49925b64fc67fde9e (Presale Agent)
    [1]:0000000000000000000000000000000000000000000000000000000000000140   offset to _saleContractType
    [2]:0000000000000000000000000000000000000000000000000000000000000000   _targetEthMin: 0 ETH
    [3]:00000000000000000000000000000000000000000000015d38b584d23a680000   _targetEthMax: new BigNumber("15d38b584d23a680000",16).shift(-18) => 6,442 ETH
    [4]:0000000000000000000000000000000000000000000771d2fa45345aa9000000   _tokensLimit: new BigNumber("771d2fa45345aa9000000", 16).shift(-18) => 9,000,000 RPL
    [5]:0000000000000000000000000000000000000000000000000000000000000000   _minDeposit: 0 ETH
    [6]:00000000000000000000000000000000000000000000015d38b584d23a680000   _maxDeposit: new BigNumber("15d38b584d23a680000",16).shift(-18) => 6,442 ETH
    [7]:0000000000000000000000000000000000000000000000000000000000000000   _startBlock: 0
    [8]:0000000000000000000000000000000000000000000000000000000000000000   _endBlock: 0
    [9]:0000000000000000000000004e3bc0dc25c42ed2745bfc67f1d0daa52103c01a   _depositAddress: 0x4e3bc0dc25c42ed2745bfc67f1d0daa52103c01a
    [10]:0000000000000000000000000000000000000000000000000000000000000007  length of _saleContractType 7 characters
    [11]:70726573616c6500000000000000000000000000000000000000000000000000  _saleContractType: web3.toUtf8("70726573616c65") => "presale"

<br />

#### Reserve Sale Agent

Reserve sale agent [0xa5b58f30ae0df88e24d16d7f1c61b7e4a9f4572b](https://etherscan.io/address/0xa5b58f30ae0df88e24d16d7f1c61b7e4a9f4572b).

The tx [0x057e28f2](https://etherscan.io/tx/0x057e28f205900a8f8ce6bc510bb278768b2bea2506af4a004ac08ae520faba36) links this contract with the token
contract and has the following instruction:

    setSaleAgentContract(address _saleAddress, string _saleContractType,
      uint256 _targetEthMin, uint256 _targetEthMax,
      uint256 _tokensLimit, uint256 _minDeposit, uint256 _maxDeposit,
      uint256 _startBlock, uint256 _endBlock, address _depositAddress)
    
    MethodID: 0xa7a8add2
    [0]:000000000000000000000000a5b58f30ae0df88e24d16d7f1c61b7e4a9f4572b   _saleAddress: 0xa5b58f30ae0df88e24d16d7f1c61b7e4a9f4572b (Reserve Sale Agent)
    [1]:0000000000000000000000000000000000000000000000000000000000000140   offset to _saleContractType
    [2]:0000000000000000000000000000000000000000000000000000000000000000   _targetEthMin: 0 ETH
    [3]:0000000000000000000000000000000000000000000000000000000000000000   _targetEthMax: > new BigNumber("23bbf4b14c2e7ff800000", 16).shift(-18) => 2,700,000 ETH
    [4]:000000000000000000000000000000000000000000023bbf4b14c2e7ff800000   _tokensLimit: new BigNumber("23bbf4b14c2e7ff800000", 16).shift(-18) => 2,700,000 RPL
    [5]:0000000000000000000000000000000000000000000000000000000000000000   _minDeposit: 0 ETH
    [6]:0000000000000000000000000000000000000000000000000000000000000000   _maxDeposit: 0 ETH
    [7]:0000000000000000000000000000000000000000000000000000000000000000   _startBlock: 0
    [8]:0000000000000000000000000000000000000000000000000000000000000000   _endBlock: 0
    [9]:0000000000000000000000004e3bc0dc25c42ed2745bfc67f1d0daa52103c01a   _depositAddress: 0x4e3bc0dc25c42ed2745bfc67f1d0daa52103c01a
    [10]:000000000000000000000000000000000000000000000000000000000000000b  length of _saleContractType 11 characters
    [11]:7265736572766546756e64000000000000000000000000000000000000000000  _saleContractType: web3.toUtf8("7265736572766546756e64") => "reserveFund"

<br />

### Crowdsale Statistics

<br />

### Crowdsale Contract

* Contributions are recorded per address and ethers (ETH) accumulated in the crowdsale contract
* After finalisation, if:
  * minimum funding goal is not met, call `claimTokensAndRefund()` to receive a refund
  * minimum funding goal is met and there is an excess in contributed ethers, call `claimTokensAndRefund()` to receive excess ethers proportional to contributions

<br />

### Token Contract

Note that the token contract was deployed before the recently finalised [ERC20 Token Standard](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20-token-standard.md)
compliant and has the following notable features:

* `transfer(...)` and `transferFrom(...)` will return false instead of throwing an error. The recent changes to the standard recommends
  the throwing of an error instead of returning false
* `transfer(...)` and `transferFrom(...)` will return false when transferring 0 tokens. The recent changes to the standard recommends that 0 value
  transfers be treated as valid transfers
* `transfer(...)` and `transferFrom(...)` have not been built with a check on the size of the data being passed. This check is
  [no longer a recommended feature](https://blog.coinfabrik.com/smart-contract-short-address-attack-mitigation-failure/)
* `approve(...)` does not have the [requirement that a non-zero approval limit be set to 0 before a new non-zero limit can be set](https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729)

There is no overflow protection in the `transfer(...)` and `transferFrom(...)` functions, but the numeric range of
the token amounts is restricted to a safe range as these amounts are determined by the amount of ethers contributed and
by `RocketPoolToken.totalSupplyCap`.


<br />

<hr />

## Table Of Contents

* [Summary](#summary)
  * [Crowdsale And Token Mainnet Addresses](#crowdsale-and-token-mainnet-addresses)
  * [Crowdsale Statistics](#crowdsale-statistics)
  * [Presale Contract](#presale-contract)
  * [Crowdsale Contract](#crowdsale-contract)
  * [Token Contract](#token-contract)
* [Table Of Contents](#table-of-contents)
* [Recommendations](#recommendations)
* [Potential Vulnerabilities](#potential-vulnerabilities)
* [Scope](#scope)
* [Limitations](#limitations)
* [Due Diligence](#due-diligence)
* [Risks](#risks)
* [Testing](#testing)
  * [Test 1 Funding Goal Reached](#test-1-funding-goal-reached)
  * [Test 2 Funding Goal Not Reached](#test-2-funding-goal-not-reached)
* [Code Review](#code-review)
* [References](#references)

<br />

<hr />

## Recommendations

* **MEDIUM IMPORTANCE** Upgrade minimum compiler version from `pragma solidity ^0.4.2;` to `pragma solidity ^0.4.13;` or `pragma solidity ^0.4.11;`.
  You may have to replace your `throw` code with `require(...)` or `assert(...)` if you upgrade to 0.4.13.
  * [x] Completed in [8147b2f2](https://github.com/darcius/rocketpool-crowdsale/commit/8147b2f2f4c535777ab5750240709748dfee0377)
* **LOW IMPORTANCE** Use the `acceptOwnership(...)` pattern in the *Owned* contracts for a much safer transfer of ownership.
  See the [example](https://github.com/openanx/OpenANXToken/blob/master/contracts/Owned.sol#L51-L55).
  * [x] Completed in [8147b2f2](https://github.com/darcius/rocketpool-crowdsale/commit/8147b2f2f4c535777ab5750240709748dfee0377)
* **LOW IMPORTANCE** Replace `uint256 public constant decimals = 18;` with `uint8 public constant decimals = 18;` in **RocketPoolToken** as `uint8`
  is meant to be the standard, although some token contracts use `uint256` and no side effects have been reported. If you use `uint8`, you will
  have to replace `10**decimals;` with `10**uint256(decimals);` in the next statement.
  * [x] Completed in [8147b2f2](https://github.com/darcius/rocketpool-crowdsale/commit/8147b2f2f4c535777ab5750240709748dfee0377)
* **LOW IMPORTANCE** Consider using a neater way for calling the SafeMath library - see
  [OpenANXToken.sol#L23](https://github.com/openanx/OpenANXToken/blob/master/contracts/OpenANXToken.sol#L23) and 
  [OpenANXToken.sol#L76-L77](https://github.com/openanx/OpenANXToken/blob/master/contracts/OpenANXToken.sol#L76-L77).
  * [x] Completed in [19372b87](https://github.com/darcius/rocketpool-crowdsale/commit/19372b8736371810ed0e5268281dc7563127a269)
* **LOW IMPORTANCE** Consider replacing the custom Arithmetic.sol library with the standard `uint` maths as the use cases in 
  *RocketPoolPresale* and *RocketPoolCrowdsale*  seems suitable for the standard `uint` maths.
  * [x] Completed in [270c5a09](https://github.com/darcius/rocketpool-crowdsale/commit/270c5a091444ed449d6dcf7cfffb85fabaaae64b)

  Example from David:

      User makes deposit of '1.3463233' ether when each token costs 0.00032 per ether.

      Excel = 4,207.260312500000000000
      Arithmetic Lib = 4207260312500000000000
      SafeMath = 4207000000000000000000
      calculated like this

      FlagUint(Arithmetic.overflowResistantFraction(allocations[msg.sender].amount, exponent, tokenPrice));
      FlagUint(SafeMath.div(allocations[msg.sender].amount, tokenPrice)*exponent);

  My testing using `geth console`:
  
      > new BigNumber("1.3463233").shift(18).mul(100000).div(32).shift(-18)
      4207.2603125
      
  My testing with further decimals using `geth console`:

      new BigNumber("1.3463233123456789").shift(18).mul(100000).div(32).shift(-18)
      4207.2603510802465625

  Sample Solidity code to test David's example:
  
      pragma solidity ^0.4.11;

      contract Test {
          uint256 public result;

          function Test() {
              uint256 ethers = 1346323300000000000; // new BigNumber("1.3463233").shift(18)
              result = ethers * 100000 / 32;
              // Result is 4207260312500000000000
              // new BigNumber("4207260312500000000000").shift(-18) => 4207.2603125
          }
      }

  Comparison of gas between RocketPool's original Arithmetic.sol and Solidity native uint256 divs shows a similar gas usage:
  
      pragma solidity ^0.4.11;
      
      // Arithmetic library borrowed from Gnosis, thanks guys!
      
      library Arithmetic {
      
          function mul256By256(uint a, uint b)
              constant
              returns (uint ab32, uint ab1, uint ab0)
          {
              uint ahi = a >> 128;
              uint alo = a & 2**128-1;
              uint bhi = b >> 128;
              uint blo = b & 2**128-1;
              ab0 = alo * blo;
              ab1 = (ab0 >> 128) + (ahi * blo & 2**128-1) + (alo * bhi & 2**128-1);
              ab32 = (ab1 >> 128) + ahi * bhi + (ahi * blo >> 128) + (alo * bhi >> 128);
              ab1 &= 2**128-1;
              ab0 &= 2**128-1;
          }
      
          // I adapted this from Fast Division of Large Integers by Karl Hasselström
          // Algorithm 3.4: Divide-and-conquer division (3 by 2)
          // Karl got it from Burnikel and Ziegler and the GMP lib implementation
          function div256_128By256(uint a21, uint a0, uint b)
              constant
              returns (uint q, uint r)
          {
              uint qhi = (a21 / b) << 128;
              a21 %= b;
      
              uint shift = 0;
              while(b >> shift > 0) shift++;
              shift = 256 - shift;
              a21 = (a21 << shift) + (shift > 128 ? a0 << (shift - 128) : a0 >> (128 - shift));
              a0 = (a0 << shift) & 2**128-1;
              b <<= shift;
              var (b1, b0) = (b >> 128, b & 2**128-1);
      
              uint rhi;
              q = a21 / b1;
              rhi = a21 % b1;
      
              uint rsub0 = (q & 2**128-1) * b0;
              uint rsub21 = (q >> 128) * b0 + (rsub0 >> 128);
              rsub0 &= 2**128-1;
      
              while(rsub21 > rhi || rsub21 == rhi && rsub0 > a0) {
                  q--;
                  a0 += b0;
                  rhi += b1 + (a0 >> 128);
                  a0 &= 2**128-1;
              }
      
              q += qhi;
              r = (((rhi - rsub21) << 128) + a0 - rsub0) >> shift;
          }
      
          function overflowResistantFraction(uint a, uint b, uint divisor)
              returns (uint)
          {
              uint ab32_q1; uint ab1_r1; uint ab0;
              if(b <= 1 || b != 0 && a * b / b == a) {
                  return a * b / divisor;
              } else {
                  (ab32_q1, ab1_r1, ab0) = mul256By256(a, b);
                  (ab32_q1, ab1_r1) = div256_128By256(ab32_q1, ab1_r1, divisor);
                  (a, b) = div256_128By256(ab1_r1, ab0, divisor);
                  return (ab32_q1 << 128) + a;
              }
          }
      }
      
      contract Test {
          uint256 n1 = 123;
          uint256 n2 = 345;
          uint256 d1 = 111;
      
          uint256 public resultNative;
          uint256 public resultArithmetic;
      
          function testNative() {
              resultNative = n1 * n2 / d1;
          }
      
          function testArithmetic() {
              resultArithmetic = Arithmetic.overflowResistantFraction(n1, n2, d1);
          }
      }

  Results using native:
  
    * Run 1 tx cost 42,066, exec cost 20,795
    * Run 2 tx cost 27,066, exec cost 5,794
    
  Results using Arithmetic:
    * Run 1 tx cost 44,014, exec cost 22,742
    * Run 2 tx cost 29,014, exec cost 7,742

  Result for Native 382, Arithmetic 382

* **LOW IMPORTANCE** Events are normally distinguished from functions by the first letter being capitalised (Upper Camel Case).
  For example `event mintToken(...);` -> `event MintToken(...);` and `event saleFinalised(...);` -> `event SaleFinalised(...);` in
  *RocketPoolToken*
  * [x] Completed in [4a3d45af](https://github.com/darcius/rocketpool-crowdsale/commit/4a3d45afaf53229ec62cd5003b843ab63d6dddc1)

* **MEDIUM IMPORTANCE** Events with the same name are defined with different number of parameters in *SalesAgent* and *SalesAgentInterface* 
  * [x] Completed in [4a3d45af](https://github.com/darcius/rocketpool-crowdsale/commit/4a3d45afaf53229ec62cd5003b843ab63d6dddc1)

* **MEDIUM IMPORTANCE** Include `Transfer(0x0, _to, _amount);` after `MintToken(msg.sender, _to, _amount);` in
  `RocketPoolToken.mint(...)` to generate a transfer event and token explorers like
  [https://etherscan.io/tokens](https://etherscan.io/tokens) and [https://ethplorer.io/](https://ethplorer.io/) will
  automatically recognise the smart contract as a token contract

  * [x] Completed in [aa76189b](https://github.com/darcius/rocketpool-crowdsale/commit/aa76189bf00d8552dd302dba37743717f75eee92)

* **LOW IMPORTANCE** Consider whether the `RocketPoolToken.approve(...)` function should have the
  [requirement that a non-zero approval limit be set to 0 before a new non-zero limit can be set](https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729).
  A [sample](https://github.com/bokkypoobah/InvestFeedCrowdsaleAudit/blob/master/contracts/StandardToken.sol#L64-L68) of the code
  required to implement this feature

  * [x] Decided not to implement.

* **MEDIUM IMPORTANCE** If possible, direct ethers contributed by participants into a multisig or hardware wallet immediately after
  being transferred to the *RocketPoolPresale* contract, and the *RocketPoolCrowdsale* contract. For the *RocketPoolCrowdsale* 
  contract that provides for refunds if the minimum funding goal is not met, transfer `this.balance` to the multisig or hardware
  wallet after the minimum funding goal is reached.

  * [x] Completed in [6672f7d2](https://github.com/darcius/rocketpool-crowdsale/commit/6672f7d2d552f59b2d35cca16021c21015450917)

<br />

<hr />

## Potential Vulnerabilities

No potential vulnerabilities have been identified in the **RocketPoolPresale** and **RocketPoolToken** contract.

No potential vulnerabilities have been identified in the **RocketPoolCrowdsale** contract.

<br />

<hr />

## Scope

This audit is into the technical aspects of the crowdsale contracts. The primary aim of this audit is to ensure that funds contributed to
these contracts are not easily attacked or stolen by third parties. The secondary aim of this audit is that ensure the coded algorithms work
as expected. This audit does not guarantee that that the code is bugfree, but intends to highlight any areas of weaknesses.

<br />

<hr />

## Limitations

This audit makes no statements or warranties about the viability of the RocketPool's business proposition, the individuals involved in
this business or the regulatory regime for the business model.

<br />

<hr />

## Due Diligence

As always, potential participants in any crowdsale are encouraged to perform their due diligence on the business proposition before funding
any crowdsales.

Potential participants are also encouraged to only send their funds to the official crowdsale Ethereum address, published on the
crowdsale organiser's official communication channel.

Scammers have been publishing phishing address in the forums, twitter and other communication channels, and some go as far as duplicating
crowdsale websites. Potential participants should NOT just click on any links received through these messages. Scammers have also hacked
the crowdsale website to replace the crowdsale contract address with their scam address.
 
Potential participants should also confirm that the verified source code on EtherScan.io for the published crowdsale address matches the
audited source code, and that the deployment parameters are correctly set, including the constant parameters.

<br />

<hr />

## Risks

* The crowdsale contract will hold contributed ETH until the crowdsale is finalised, and could be a target for hackers. Once the target ETH
  is reached, these funds fill be moved into the crowdsale wallet, but any excess contributions over the target ETH will accumulated in the
  crowdsale contract

<br />

<hr />

## Testing

The original tests were conducted on the presale sequence of contracts. Now that the presale phase is complete, the test have been updated
to the main crowdsale.

### Test 1 Funding Goal Reached

The following functions were tested using the script [test/01_test1.sh](test/01_test1.sh) with the summary results saved
in [test/test1results.txt](test/test1results.txt) and the detailed output saved in [test/test1output.txt](test/test1output.txt):

* [x] Deploy the token and sale contracts
* [x] Configure sale
* [x] Verify deposit address
* [x] Contribute to the crowdsale contract
* [x] Finalise crowdsale
* [x] Claim tokens and refunds
* [x] Transfer tokens

<br />

### Test 2 Funding Goal Not Reached

The following functions were tested using the script [test/02_test2.sh](test/02_test2.sh) with the summary results saved
in [test/test2results.txt](test/test2results.txt) and the detailed output saved in [test/test2output.txt](test/test2output.txt):

* [x] Deploy the token and sale contracts
* [x] Configure sale
* [x] Verify deposit address
* [x] Contribute to the crowdsale contract
* [x] Finalise crowdsale
* [x] Claim tokens and refunds

<br />

<hr />

## Code Review

* [x] [code-review/lib/SafeMath.md](code-review/lib/SafeMath.md)
* [x] [code-review/base/Owned.md](code-review/base/Owned.md)
  * [x] contract Owned
* [x] [code-review/base/StandardToken.md](code-review/base/StandardToken.md)
  * [x] contract Token
  * [x] contract StandardToken is Token
* [x] [code-review/RocketPoolToken.md](code-review/RocketPoolToken.md)
  * [x] contract RocketPoolToken is StandardToken, Owned
    * [x] using SafeMath for uint
* [x] [code-review/interface/SalesAgentInterface.md](code-review/interface/SalesAgentInterface.md)
  * [x] contract SalesAgentInterface
* [x] [code-review/base/SalesAgent.md](code-review/base/SalesAgent.md)
  * [x] contract SalesAgent
* [x] [code-review/sales/RocketPoolPresale.md](code-review/sales/RocketPoolPresale.md)
  * [x] contract RocketPoolPresale is SalesAgent, Owned
    * [x] using SafeMath for uint
* [x] [code-review/sales/RocketPoolCrowdsale.md](code-review/sales/RocketPoolCrowdsale.md)
  * [x] contract RocketPoolCrowdsale is SalesAgent
    * [x] using SafeMath for uint
* [x] [code-review/sales/RocketPoolReserveFund.md](code-review/sales/RocketPoolReserveFund.md)
  * [x] contract RocketPoolReserveFund is SalesAgent

<br />

### Not Reviewed

The following contracts have not been reviewed as they are part of the Truffles testing framework:

* [ ] [code-review/Migrations.md](code-review/Migrations.md)
  * [ ] contract Migrations

<br />

<hr />

## References

* [Ethereum Contract Security Techniques and Tips](https://github.com/ConsenSys/smart-contract-best-practices)

<br />

<br />

Enjoy. (c) BokkyPooBah / Bok Consulting Pty Ltd for RocketPool Oct 28 2017. The MIT Licence.