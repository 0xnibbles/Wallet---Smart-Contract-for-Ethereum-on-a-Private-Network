##### Version 1.0
##### Author: s4nkx0k


# Ethereum Tutorial

## Wallet - Smart Contract for Ethereum on a Private Network

`### Tested in MacOs`

***

### Termos

* **DApp** - Decentralized App - [What is a DApp?](https://ethereum.stackexchange.com/questions/383/what-is-a-dapp);
* **Swarm** - Decentralized Storage on the Ethereum network - [What is Swarm?](https://ethereum.stackexchange.com/questions/375/what-is-swarm-and-what-is-it-used-for)(P.S. A explicação exata não sei);


### Useful links

- [x] - [Ethereum e a Blockchain](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/Ethereum%20e%20a%20Blockchain.md)- Explicação simples de como a rede Ethereum utliza a blockchain para realizar contratos e transações;

- [x] - [Remix Solidity IDE](https://remix.ethereum.org/#optimize=false&version=soljson-v0.4.19+commit.c4cbbb05.js) -> IDE Solidity online para testar a programação dos smart contracts com debugger e ambiente de teste integrado, análise estatística e várias contas disponíveis para poder simular transações entre elas. Além de desenvolver o programa também se pode fazer o deploy porque O Remix compila os contratos;

- [x] - [Solidity](https://solidity.readthedocs.io/en/develop/) -> Documentação da linguagem Solidity;

- [x] - [Ethereum Project](https://www.ethereum.org/) -> Página principal do projeto Ethereum;

- [x] - [GO Ethereum Client (Geth)](https://github.com/ethereum/go-ethereum/wiki/geth) -> é interface de linha de comandos que permite correr um nó da blockchain Ethereum implementado em GO. Pode conectar-se a outros nós, dá acesso à blockchain e também ser usado para minerar [Download Page](https://ethereum.github.io/go-ethereum/downloads/);

- [x] - [Mist Wallet](https://github.com/ethereum/mist/wiki) -> é uma aplicação que utiliza a framework [electron](https://github.com/electron/electron), ou seja é uma aplicação híbrida para desktop com uma interface web com acesso à [Ethereum Wallet](https://github.com/ethereum/meteor-dapp-wallet). Compatível com Windows, Linux e MacOs [Download MIST](https://github.com/ethereum/mist/releases);

- [x] - [Udemy - Curso grátis de Introdução à rede Ethereum](https://www.udemy.com/blockchain-application/)

### Lets explore the Ethereum network

* Steps:

    1. Download and install **Geth**;
    2. Download and install **MIST**;
    3. Cretae the file **genesis.json**[Example](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/genesis.json);
    4. Start a new private chain:
         `geth --datadir=/path/to/an/empty/directory init /path/to/genesis.json`
    5. Start geth with:
        * `geth --datadir=/path/to/the/chaindata/directory/above`
    6. Programming and testing a smart contract on Remix:
        *  On **Run** tab:
                - Colocar Environment em "JavaScript VM" para uma blockchain simulada;
                - Accounts -> contas disponiveís com ether para testar transações;
                - Gas Limit -> limit de gas a ser usado nesse contrato;
                - Value -> valor a transferir em wei, gwei, finney ou ether([Conversor para ether](https://etherconverter.online/));
                - Exemplo de um contrato em Solidity em [Smart Wallet on Ethereum](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/wallet.sol);
    6. After programming the functions click on **Create**  to create the contract. If there are errors a warning will be issued in the log window (gray window) otherwise the functions are available logod and then to be executed. All transactions made are available in the log window with all relative information (transaction cost and execution, hash, source and destination address, etc);
    7. OPen MIST with (example for **MACOS**):
        * `/Applications/Mist.app/Contents/MacOS/Mist --rpc path/to/geth.ipc --swarmurl="http://swarm-gateways.net"` 
    8. Go to the **Contracts** tab and click **Up New Contract**. Set copy remix code to area **Source code in Solidity**. Before creating you can also transfer ether to the contract at .... Once added and completed without errors the code will appear the contract functions.
    9. At the end of the page click on **Up**;
    10. Since the ethereum network is based on the blockchain, it is necessary to get miners to work to validate the creation and the transactions made in the contract. To enable this feature, follow these steps:
        * Abrir nova consola e colocar o comando **geth attach path/to/geth.ipc**. Este comando abre uma **geth console** para poder interagir com a instância do Geth. A partir daqui temos uma *geth console*;
        * Para iniciar o "trabalho" dos mineradores fazer na geth console o comando `miner.start(número de threads a usar)`. Quanto maior o número de threads mais rápido ocorre o processo de mineração. Mais informações sobre a API do Geth em [Geth API](https://github.com/ethereum/go-ethereum/wiki/Management-APIs);
        * Quando ocorrerem o número minímo de confirmações o contrato ficará disponível na rede privada para ser usado, tal como acontece na rede Ethereum;
    11. Voltar de novo ao **MIST** e verificar que no separdor **Contratos** se o contrato que acabamos de criar está disponível e clicar nele;
    12. Ao abrir deverá de aparecer todas as informações relativas ao contrato, bem como as funções que foram programadas e estão prontas a utilizar. **Não esquecer** que depois realizar alguma função é necessário ter mineradores para realizar as confirmações.



***


