##### Version 1.0
##### Author: EduardoSilva


# Ethereum Tutorial

## Wallet - Smart Contract for Ethereum on a Private Network

`### Tested in MacOs`

***

### Termos

* **DApp** - Decentralized App - [What is a DApp?](https://ethereum.stackexchange.com/questions/383/what-is-a-dapp);
* **Swarm** - Decentralized Storage on the Ethereum network - [What is Swarm?](https://ethereum.stackexchange.com/questions/375/what-is-swarm-and-what-is-it-used-for)(P.S. A explicação exata não sei);


### Links úteis

- [x] - [Ethereum e a Blockchain](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/Ethereum%20e%20a%20Blockchain.md)- Explicação simples de como a rede Ethereum utliza a blockchain para realizar contratos e transações;

- [x] - [Remix Solidity IDE](https://remix.ethereum.org/#optimize=false&version=soljson-v0.4.19+commit.c4cbbb05.js) -> IDE Solidity online para testar a programação dos smart contracts com debugger e ambiente de teste integrado, análise estatística e várias contas disponíveis para poder simular transações entre elas. Além de desenvolver o programa também se pode fazer o deploy porque O Remix compila os contratos;

- [x] - [Solidity](https://solidity.readthedocs.io/en/develop/) -> Documentação da linguagem Solidity;

- [x] - [Ethereum Project](https://www.ethereum.org/) -> Página principal do projeto Ethereum;

- [x] - [Cliente GO Ethereum (Geth)](https://github.com/ethereum/go-ethereum/wiki/geth) -> é interface de linha de comandos que permite correr um nó da blockchain Ethereum implementado em GO. Pode conectar-se a outros nós, dá acesso à blockchain e também ser usado para minerar [Download Page](https://ethereum.github.io/go-ethereum/downloads/);

- [x] - [Mist Wallet](https://github.com/ethereum/mist/wiki) -> é uma aplicação que utiliza a framework [electron](https://github.com/electron/electron), ou seja é uma aplicação híbrida para desktop com uma interface web com acesso à [Ethereum Wallet](https://github.com/ethereum/meteor-dapp-wallet). Compatível com Windows, Linux e MacOs [Download MIST](https://github.com/ethereum/mist/releases);

- [x] - [Udemy - Curso grátis de Introdução à rede Ethereum](https://www.udemy.com/blockchain-application/)

### Vamos lá colocar as mãos na massa e entrar no mundo da rede Ethereum

* Passos:

    1. Download e instalar **Geth**;
    2. Download e instalar **MIST**;
    3. Criar o ficheiro **genesis.json**[Exemplo](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/genesis.json);
    4. Inicializar uma nova cadeia privada com:
         `geth --datadir=/path/to/an/empty/directory init /path/to/genesis.json`
    5. Iniciar geth com:
        * `geth --datadir=/path/to/the/chaindata/directory/above`
    6. Programar e testar smart contract no Remix
        *  No separador **Run**:
                - Colocar Environment em "JavaScript VM" para uma blockchain simulada;
                - Accounts -> contas disponiveís com ether para testar transações;
                - Gas Limit -> limit de gas a ser usado nesse contrato;
                - Value -> valor a transferir em wei, gwei, finney ou ether([Conversor para ether](https://etherconverter.online/));
                - Exemplo de um contrato em Solidity em [Smart Wallet on Ethereum](https://github.com/uminho-mieti-crypto/1718-G2/blob/master/Projeto%20Pr%C3%A1tico%20Smart%20Contract-Eduardo%20A70216/ethereum/wallet.sol);
    6. Depois programar as funções clicar em **Create*** para criar contrato. Se existirem erros será emitido um aviso na janela de logs (janela cinzenta) senão, as funções estaram disponíveis logod e seguida para serem executadas. Todas as transações efectuadas ficam disponíveis na janela de logs com todas as informações relativas(custo da transação e execução, hash, endereço de origem e de destino,etc);
    7. Abrir o MIST com (exemplo para **MACOS**):
        * `/Applications/Mist.app/Contents/MacOS/Mist --rpc path/to/geth.ipc --swarmurl="http://swarm-gateways.net"` 
    8. Ir ao separador **Contratos** e clicar em **Subir Novo contrato**. Definir copiar código do remix para a área **Código fonte em Solidity** . Antes de criar pode tambén transferir ether para o contrsto em .... Depois de adicionado e compliado sem erros o código irão aparecer as funções do contrato.
    9. No fim da página clicar em **Subir**;
    10. Como a rede ethereum se baseia na blockchain, é necessário colocar mineradores a funcionar para validar a criação e as transações efectuados no contrato. Para ativar esta funcionalidade efetuam-se os seguintes passos:
        * Abrir nova consola e colocar o comando **geth attach path/to/geth.ipc**. Este comando abre uma **geth console** para poder interagir com a instância do Geth. A partir daqui temos uma *geth console*;
        * Para iniciar o "trabalho" dos mineradores fazer na geth console o comando `miner.start(número de threads a usar)`. Quanto maior o número de threads mais rápido ocorre o processo de mineração. Mais informações sobre a API do Geth em [Geth API](https://github.com/ethereum/go-ethereum/wiki/Management-APIs);
        * Quando ocorrerem o número minímo de confirmações o contrato ficará disponível na rede privada para ser usado, tal como acontece na rede Ethereum;
    11. Voltar de novo ao **MIST** e verificar que no separdor **Contratos** se o contrato que acabamos de criar está disponível e clicar nele;
    12. Ao abrir deverá de aparecer todas as informações relativas ao contrato, bem como as funções que foram programadas e estão prontas a utilizar. **Não esquecer** que depois realizar alguma função é necessário ter mineradores para realizar as confirmações.



***


