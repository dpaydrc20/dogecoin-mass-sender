# dogecoin-mass-sender work in progress

Here's a GitHub repository `README.md` file to explain how to use the provided Dogecoin batch sending script. This will help users understand how to set up and run the script.

```markdown
# Dogecoin Batch Sender

This script allows you to send Dogecoin to multiple addresses in batches using Dogecoin Core's JSON-RPC interface.

## Prerequisites

- Node.js installed
- Dogecoin Core installed and running with JSON-RPC enabled

## Configuration

1. Clone this repository:

    ```sh
    git clone https://github.com/yourusername/dogecoin-batch-sender.git
    cd dogecoin-batch-sender
    ```

2. Install the required dependencies:

    ```sh
    npm install axios
    ```

3. Update the configuration in `index.js` with your Dogecoin Core RPC credentials:

    ```javascript
    const rpcUser = 'yourrpcusername';
    const rpcPassword = 'yourrpcpassword';
    const rpcPort = 22555; // Default port for Dogecoin Core
    const rpcHost = '127.0.0.1';
    const rpcUrl = `http://${rpcUser}:${rpcPassword}@${rpcHost}:${rpcPort}/`;
    ```

## Usage

1. Define the addresses and amounts you want to send in `index.js`:

    ```javascript
    const addressesAmounts = {
        "D6K8aym7xs3eXBdMJm9Uj3pRcbXgV8zZSo": 10.0,  // Address 1 with 10 DOGE
        "DMwWH9GsGy2HQ4iujYpFdPiSv3p6V12Gyj": 5.0,   // Address 2 with 5 DOGE
        "D7VFRZvcQ3xLbgpSL2gmsGh3cWZxLLpv3D": 2.5,   // Address 3 with 2.5 DOGE
        // Add more addresses as needed...
    };
    ```

2. Run the script:

    ```sh
    node index.js
    ```

The script will send Dogecoin to the specified addresses in batches and wait for each transaction to be confirmed before proceeding to the next batch.

## Functions

### `sendDogeToAddressesInBatches(addressesAmounts, batchSize = 24)`

Sends Dogecoin to multiple addresses in batches. The `batchSize` parameter determines how many addresses are included in each batch.

### `sendBatch(batch)`

Sends a batch of transactions using the `sendmany` method.

### `waitForConfirmation(txid, confirmationsRequired = 1)`

Waits for a transaction to be confirmed.

## Example

Here is an example of how to use the script:

```javascript
const addressesAmounts = {
    "D6K8aym7xs3eXBdMJm9Uj3pRcbXgV8zZSo": 10.0,  // Address 1 with 10 DOGE
    "DMwWH9GsGy2HQ4iujYpFdPiSv3p6V12Gyj": 5.0,   // Address 2 with 5 DOGE
    "D7VFRZvcQ3xLbgpSL2gmsGh3cWZxLLpv3D": 2.5,   // Address 3 with 2.5 DOGE
    // Add more addresses as needed...
};

sendDogeToAddressesInBatches(addressesAmounts);
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

Replace the placeholders like `yourrpcusername`, `yourrpcpassword`, and `yourusername` with actual values. Save this content as `README.md` in your repository. This documentation will help others understand how to use your script effectively.
