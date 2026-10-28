# Privacy Policy — Pockit

**Last updated:** October 28, 2026  
**Effective:** as of the date of publication

This policy describes how the **Pockit** mobile application (the "App") handles your information, in compliance with Colombia's Statutory Law 1581 of 2012 and Decree 1377 of 2013, and with Apple's App Store privacy guidelines.

## 1. Data controller

- **Name:** Juan Marulanda (natural person, independent developer)
- **Domicile:** Bogotá, Colombia
- **Contact email:** feedbackpockit@gmail.com

## 2. Core principle: your data stays on your device

Pockit runs **on your iPhone and, by default, with no connection to servers**. Except for the optional automatic import features (section 7), the App:

- **Does not collect, transmit, or store** your personal or financial data on any server, ours or third-party.
- **Does not require an account** or any identifying information.
- **Uses no analytics, advertising, or tracking** of any kind, and includes no third-party SDKs.
- The developer **has no access** to the information you record in the App.

If you do not enable automatic import (SMS or Apple Pay), no data leaves your device. The App Store privacy label reflects only the processing described in section 7: financial information, an installation identifier, and the subscription's purchase history, all **not linked to your identity** and used solely for App functionality and abuse prevention.

## 3. Information the App stores locally on your device

Although no data is collected, the App stores locally, solely to function:

- **Financial data you enter:** transactions (expenses, income, savings), amounts, categories, notes, dates, savings goals, category budgets, recurring-transaction rules, and recent searches. These are kept in a local database encrypted by iOS with complete data protection (`NSFileProtectionComplete`).
- **Non-sensitive preferences:** theme, color palette, language, and spending-pace settings, stored in the App's local preferences. No financial data is stored there.
- **Lock configuration:** the biometric-lock preference is stored in the system Keychain, restricted to this device and accessible only while the device is unlocked.

## 4. Face ID / Touch ID

If you enable the App lock, authentication is performed by iOS through the `LocalAuthentication` framework. The App **only receives the result (success or failure)**: it never accesses your biometric data, which remains under the exclusive control of Apple and your device's Secure Enclave.

## 5. Backups

If you have device backups enabled (iCloud or computer), Pockit's local database may be included in them. Those backups are managed by Apple according to your settings and Apple's privacy policy. Keys Pockit stores in the Keychain **do not migrate** to backups or other devices.

## 6. Data export (CSV)

The App lets you export your transactions to a CSV file. This happens **only when you initiate it**, and you decide where to share or save the file. Once exported, protecting that file is your responsibility.

## 7. Automatic transaction import (optional features)

Pockit can log transactions for you in two ways, both **off by default** and both based on Apple Shortcuts automations that you create and control yourself. You can have either, both, or neither enabled.

### 7.1 From your bank's SMS messages

Pockit can log transactions automatically from your bank's SMS messages, through an Apple Shortcuts automation that you create and control yourself. This feature is **off by default** and only works if you enable it in Settings.

- The App **does not read your messages**: it only receives the text of the SMS messages that your own Shortcuts automation sends to it (for example, your bank's).
- With the feature on, that text —along with your **category names** (so the expense can be classified into one of them)— is sent **encrypted (HTTPS)** to a server operated by the developer, which processes it with an artificial-intelligence provider (**Anthropic**) solely to extract the transaction's amount, merchant, and category.
- The SMS text is **not stored** on the server or by the AI provider (Anthropic does not use API data to train models), and it is **not linked to your identity**: the App sends no name, phone number, or accounts; only the random identifier described in section 7.3.
- Only the resulting amount, merchant, and category are saved on your device, like any transaction you enter by hand.
- If you correct the category of an imported transaction, that correction is stored **on your device only**, so texts from that merchant are filed the same way from then on; it is never sent to the server. You can review and delete it in Settings → Automation → "Category corrections".
- If there is no connection when the SMS arrives, the App stores the text **temporarily on your device, encrypted** (iOS complete data protection), to retry processing it when connectivity returns (when you open the App or another SMS arrives). That text is **deleted as soon as it is processed** or discarded, and is never sent while offline. If it cannot be processed after several days, it is deleted automatically.
- You can turn the feature off at any time in Settings and delete the automation from the Shortcuts app.

### 7.2 From your Apple Pay payments

Pockit can log the contactless payments you make with Apple Pay, using the Shortcuts "Transaction" automation. This feature is **off by default** and only runs if you turn it on in Settings.

- The App **has no access to Wallet**, to your transaction history, or to your card details. It only receives the amount and merchant name that your own Shortcuts automation hands to it, and only for contactless payments made with your iPhone or Apple Watch.
- The **amount never leaves your device**: it comes from your iPhone and is stored as is.
- To pick a category, only the **merchant name** is sent **encrypted (HTTPS)**, together with the **names of your categories**, to the same server described in section 7.1. That name is neither stored nor linked to your identity.
- If you have previously corrected the category for that merchant, classification happens **on your device only** and nothing is sent to the server.
- If you are offline (or your phone is locked and the App can't open your data yet), the transaction is **still logged** with its correct amount and stays in the "Other" category for now. The next time you open the App with a connection, the merchant name is sent to choose the category, as described above. If that doesn't happen within 14 days, the transaction stays in "Other".
- If the same charge arrives through both paths (the Apple Pay payment and your bank's SMS), the App detects it and keeps **a single transaction**.
- You can turn the feature off at any time in Settings and delete the automation from the Shortcuts app.

### 7.3 Free plan, Pockit Pro, and App verification

The features in sections 7.1 and 7.2 use artificial intelligence, which has a cost per use. The free plan includes a limited number of **automatic entries per month** (each SMS read and each Apple Pay payment categorized counts as one); **Pockit Pro** has no such limit. Recording an Apple Pay payment does not count, only choosing its category. To keep that count and prevent abuse:

- When installed, the App generates a **random identifier** that is unrelated to your name, phone number, Apple ID, or accounts, and sends it with each request described in sections 7.1 and 7.2. The server stores **only** that identifier, the month, and the number of uses; that count is **deleted automatically after 70 days**. So that reinstalling does not reset the count, the identifier is kept in your iPhone's Keychain even if you delete the App.
- To check that requests come from the genuine App and not from another program, the App uses Apple's **App Attest**: your iPhone generates a key and the server stores only its **public key**, with no data about you.
- If you have Pockit Pro, the App sends the **Apple-signed proof of purchase** (product, dates, and Apple's transaction number) to verify the subscription. The server stores that transaction number together with the identifiers of the installations using it (up to 10), to prevent a subscription from being shared. It **does not receive** your name, email, or payment method: Apple handles those.
- If you are on the free plan and have already used the month's automatic entries, the text of incoming SMS is stored **on your device, encrypted, without being sent**, for up to **60 days**: if you subscribe to Pockit Pro it is processed then (with the date it arrived); otherwise it is deleted.
- None of this data is used for advertising or shared with third parties.

## 8. System permissions

Pockit only requests, optionally, the **Face ID** permission to protect access to the App. It does not request access to location, contacts, camera, microphone, photos, or any other device data. The App has no access to your messages or to Wallet: SMS messages and payment data only reach Pockit if your Shortcuts automation sends them to it.

## 9. Retention and deletion

Your data remains on your device until you delete it. You can:

- Delete individual transactions, goals, or categories within the App.
- Use **"Delete account"** in Settings, which permanently erases all transactions, budgets, and goals stored on the device.
- Uninstall the App, which removes its local database.

The server does not store your transactions. It keeps only the technical data in section 7.3: the random identifier with its monthly count (deleted automatically after 70 days), the App Attest public key and, if you are Pro, Apple's transaction number. You can request their deletion at the contact email.

## 10. Your rights (habeas data)

Under articles 8, 14, and 15 of Law 1581 of 2012, you have the right to know, update, rectify, and delete your information, and to revoke any authorization. Because of the App's local-only design, **you exercise these rights directly and without intermediaries**, by editing or deleting your information inside Pockit.

For questions or claims regarding this policy, write to **feedbackpockit@gmail.com**. Inquiries will be answered within a maximum of ten (10) business days and claims within a maximum of fifteen (15) business days from receipt, as required by law. If you believe your rights have been violated, you may contact Colombia's **Superintendence of Industry and Commerce (SIC)** — [www.sic.gov.co](https://www.sic.gov.co) — after first raising the inquiry or claim with the controller.

## 11. Minors

Pockit is not directed at minors and does not collect data from anyone, including minors. Processing of children's and adolescents' data is subject to article 7 of Law 1581 of 2012.

## 12. Changes to this policy

Any change will be published on this page and reflected in the "last updated" date. If a change involved new processing purposes, it would be announced before taking effect through the App or the App Store listing.

## 13. Contact

Juan Marulanda — feedbackpockit@gmail.com
