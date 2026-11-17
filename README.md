# Worldwide Android Crypto Wallet Finder v1.0

## Included
- Native Kotlin + Jetpack Compose Android Studio source.
- Public-address lookup for Bitcoin, Ethereum, BNB Smart Chain, Polygon, Base, Arbitrum One and Solana.
- BTC balance estimate and transaction counts using Blockstream Esplora.
- EVM native balance and current block using public JSON-RPC.
- Solana native balance using Solana public JSON-RPC.
- Personal recovery checklist with no secret-key entry field.

## Build / install APK
1. Install Android Studio and Android SDK Platform 35; use the bundled JDK 17.
2. Open this project folder in Android Studio.
3. Wait for Gradle sync and accept installation of required SDK components.
4. Connect Android phone with USB debugging enabled, or start an emulator; press Run.
5. To build an APK: Build > Build Bundle(s) / APK(s) > Build APK(s).
6. Debug APK output: `app/build/outputs/apk/debug/app-debug.apk`.
7. For distribution, use Build > Generate Signed Bundle / APK and protect the signing key.

Minimum Android: 8.0 (API 26). Internet is required for public lookups.

## Important limits
“Worldwide” here means the seven supported networks, not every crypto network or a global registry of lost wallets. This version does not search arbitrary addresses automatically, identify wallet owners, scan other apps' private storage, crack encryption, or recover seed phrases. An inactive address is not proof of abandonment. Public balance/history does not prove ownership or access.

This starter does not yet index ERC-20/BEP-20/SPL token holdings or complete transaction histories for all supported networks. Public RPC endpoints can rate-limit or change. For production use, configure reputable providers, API keys where required, privacy policy, caching, and provider failover.

Never enter or share a seed phrase/private key in this app or with recovery agents. Only recover wallets you own using the original provider's official recovery flow.

## Publish on GitHub and build APK automatically

1. Create a new **public or private** repository on GitHub named `WorldwideCryptoWalletFinder`. Do not initialize it with a README (this project already has one).
2. Extract this ZIP on your computer and open a terminal in the extracted `WorldwideCryptoWalletFinder` folder.
3. Run:

```bash
git init
git add .
git commit -m "Initial Worldwide Crypto Wallet Finder"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/WorldwideCryptoWalletFinder.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. GitHub will ask you to authenticate; use GitHub's browser/device login or a personal access token when prompted. Never put a token in source code.

4. On GitHub, open **Actions**. The included workflow builds a debug APK on pushes to `main`.
5. Open the successful workflow run, scroll to **Artifacts**, and download `worldwide-wallet-finder-debug-apk`.

The workflow produces a debug APK for testing. For a public release, create a signed release build locally or configure secure signing secrets in GitHub Actions. Never commit signing keys or passwords.
