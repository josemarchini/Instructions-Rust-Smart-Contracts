
Comandos importantes Rust:

// Correr un contrato inteligente 

Vamos a instalar el NEAR CLI, para esto simplemente ejecutamos en nuestra consola este comando:
npm install -g near-cli.
Necesitamos tener instalado Node y npm para este propósito.
Haremos Login con nuestra wallet en el CLI:
near login.
Tus credenciales serán almacenados en la carpeta ~/.near-credentials.
Ahora necesitamos compilar nuestro código, para ello utilizaremos el siguiente comando:
cargo build --target wasm32-unknown-unknown --release.
Esto generará un .wasm listo para ser deployado, se encuentra en la carpeta target.
Ahora, para hacer deploy a nuestro wasm, simplemente ejecutaremos el siguiente comando (cambiando los valores por nuestros datos).
near deploy --wasmFile target/wasm32-unknown-unknown/release/<NAME_OF_YOUR_PROYECT>.wasm --accountId < YOUR_ACCOUNT_HERE >.
Este contrato ahora está en la testnet, si quieres cambiar la red, puedes ejecutar este comando:
export NEAR_ENV=< RED_TO_BE_USED >.
Por ejemplo, para la main net: export NEAR_ENV=mainnet.
Para ejecutar los comandos de nuestro contrato, este es el comando:
near call < YOUR_ACCOUNT_HERE > < NAME_OF_FUNCTION > --accountId < YOUR_ACCOUNT_HERE >.
< NAME_OF_FUNCTION > representa la función que quieres ejecutar, en nuestro ejemplo son increment, decrement, reset, get_num, etc.


si necesitas mas comandos o ayuda puedes consultar el siquiente link donde encontraras todos los comandos para Near Cli... 

https://docs.near.org/tools/near-cli#near-login 
