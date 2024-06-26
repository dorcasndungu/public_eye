# Public Eye

A web3 (d)App for aspiring journalists, lawyers or justice seekers to follow up, record and track progress of cases in the public eye to ensure they don't go unsolved.

Wireframes
![WhatsApp Image 2024-02-26 at 10 47 00 PM](https://github.com/dorcasndungu/public_eye/assets/93251516/fc27f52f-ccf0-4404-94dc-4231ebbda16f)
![WhatsApp Image 2024-02-26 at 10 47 01 PM](https://github.com/dorcasndungu/public_eye/assets/93251516/05acffa0-4644-4356-9f57-d99ba9bc0c5b)
![WhatsApp Image 2024-02-26 at 10 47 02 PM](https://github.com/dorcasndungu/public_eye/assets/93251516/8e0da235-af7f-4ea7-89cd-c0fa297640d4)
![WhatsApp Image 2024-06-02 at 11 59 57 PM](https://github.com/dorcasndungu/public_eye/assets/93251516/b0b2e89d-430b-4861-a803-708249a080f3)


If you want to start working on your project right away, you might want to try the following commands:

```bash
cd follow_up/
dfx help
dfx canister --help
```

## Running the project locally

If you want to test your project locally, you can use the following commands:

```bash
# Starts the replica, running in the background
dfx start --background

# Deploys your canisters to the replica and generates your candid interface
dfx deploy
```

Once the job completes, your application will be available at `http://localhost:4943?canisterId={asset_canister_id}`.

If you have made changes to your backend canister, you can generate a new candid interface with

```bash
npm run generate
```

at any time. This is recommended before starting the frontend development server, and will be run automatically any time you run `dfx deploy`.

If you are making frontend changes, you can start a development server with

```bash
npm start
```

Which will start a server at `http://localhost:8080`, proxying API requests to the replica at port 4943.

### Note on frontend environment variables

If you are hosting frontend code somewhere without using DFX, you may need to make one of the following adjustments to ensure your project does not fetch the root key in production:

- set`DFX_NETWORK` to `ic` if you are using Webpack
- use your own preferred method to replace `process.env.DFX_NETWORK` in the autogenerated declarations
  - Setting `canisters -> {asset_canister_id} -> declarations -> env_override to a string` in `dfx.json` will replace `process.env.DFX_NETWORK` with the string in the autogenerated declarations
- Write your own `createActor` constructor
