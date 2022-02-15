# ERC20 Token

Creazione di un ERC-20 standard Ethereum Token.

## Erc-20

ERC-20 è l'interfaccia standard. 

Il seguente standard consente l'implementazione di un'API standard per i token all'interno degli Smart Contract. 

Per maggiori informazioni riguardo Solidity Language e lo Standard ERC-20 Standard consultare i seguenti link

- [Solidity](https://solidity.readthedocs.io/en/v0.6.8/): 
- [ERC-20](https://ethereum.org/it/developers/docs/standards/tokens/erc-20/)

### Contract

Il contratto eredita le funzioni presenti nell'interfaccia standard _IERC20_ la quale contiene tutte le funzioni con le relative
dichiarazioni ed il corpo vuoto.
Quest'ultimo viene inizializzato e compilato nel contratto che lo eredita.

### Constructor

Il `constructor` setta il `name`, `symbol`, `decimals` e `totalSupply` del token ed il balance del msg.sender.

### Balance

La view function `balanceOf` ritorna il balance dell'address di un `account`.

### Transfer and Transfer From

La funzione `transfer` viene chiamata da un account e trasferisce un certo `amount` di token, ad un altro address `recipient`.

La funzione `transferFrom` permette ad un account che non sia l'owner di trasferire `amount` , un certo numero di token, da un determinato address `sender` ad un altro `recipient`.

Entrambe le funzioni fanno un trigger  dell'evento di `Transfer`.

### Approve

La funzione di `approve` permette ad un account `spender` di poter utilizzare un certo `amount` di token tramite l'approvazione dell'`owner`.


### Allowance

La view function `allowance` ritorna il valore che l'address `spender` è abilitato a spendere tramite il permesso dell'`owner`.

## Erc-20 imports

### IERC20 

Il contratto eredita le funzioni presenti nell'interfaccia standard _IERC20_ la quale contiene tutte le funzioni con le relative
dichiarazioni ed il corpo vuoto.
Quest'ultimo viene inizializzato e compilato nel contratto che lo eredita.

### Ownable

Il contratto Ownable fornisce un meccanismo di controllo degli accessi di base, in cui è presente un account (un proprietario) a cui può essere concesso l'accesso esclusivo a funzioni specifiche.

Questo modulo viene utilizzato attraverso l'ereditarietà.

Renderà disponibile il modificatore `onlyOwner`, che può essere applicato alle funzioni per limitarne l'uso al proprietario.

Di default, l'`owner` sarà colui che distribuisce il contratto e l'indirizzo può essere modificato con il metodo `transferOwnership`.

### Context

Il contratto Context fornisce informazioni sul contesto di esecuzione corrente:
mittente della transazione e i suoi dati. 

# Sale Contract 
Creazione di uno smart contract per l'acquisto e vendita dei token.

### Contract
Il contratto importa il token ERC20.

### Constructor

Il `constructor` imposta l'`admin`, `tokenContract` ovvero l'interazione con il contratto del token, `tokenPrice` ovvero il prezzo del token stabilito in fase di deploy.

### buyTokens

La payable function `buyTokens` permette l'acquisto di un determinato `_numberOfTokens` e fa un trigger dell'evento di Sell.

### endSale
La funzione di `endSale` ritorna tutti i tokens non venduti all'admin del contratto e può essere richiamata solo da quest'ultimo.

### Requisiti per l'utilizzo della repository

Compilazione, tests e dedploy del contratto possono essere eseguiti con l'ausilio del framework *Truffle*.

- [Node.js](https://nodejs.org/download/release/latest-v10.x/)
- [Truffle](https://www.trufflesuite.com/truffle)

## Usage

Lanciare da terminale il seguente comando:

```sh
npm install
npm install -g truffle
```
Tutte le dipendenze relative al progetto e Truffle verranno installate globalmente.

### Compile contracts

Utilizzando il seguente comando:
```sh
truffle compile
```
 saranno disponibili nella cartella `build/contracts/`informazioni relative al contratto in formato JSON come l'ABI, l'address ecc..


### Run tests on Truffle
 
È possibile fare un test dei file presenti nella cartella `/test` lanciando da terminale il comando:

```sh
truffle test
```

### Run migration and deploy contracts

Comando per la migrate:

```sh
truffle migrate --reset --network development // mainnet, rinkeby, polygon, mumbai...
```

Dopo la migration, potrai visualizzare l'address del deployer e del contratto.
