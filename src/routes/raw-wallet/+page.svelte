<script lang="ts">
    import { PrivateKey } from '@bsv/sdk';

    let WIF: string;
    let address: string;

    function createKeys(): void {
        try {
            const privKey = PrivateKey.fromRandom();
            WIF = privKey.toWif();
            console.log("Private key WIF format is :", WIF);
            address = privKey.toAddress();
            console.log("Your bitcoin address is:", address);
        } catch (error) {
            console.error("Error generating keys:", error);
        }
    }
</script>

<section>
    <button class = " bg-black text-white pd-3 rounded-md text-center
    "on:click={createKeys}>Generate New Wallet Keys</button>
    <p>Private Key WIF format is {WIF}</p>
    <p>Your BitCoin Address is {address}</p>
</section>
