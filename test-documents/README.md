# sentinel-trade-terminal
SentinelTrade automates bank trade screening using Gemini to detect sanctions and dual-use goods in real-time, turning manual document checks into instant, audit-ready decisions.

🛠️ Testing Instructions
To evaluate SentinelTrade, please follow these step-by-step audit scenarios using the Google AI Studio app link and the sample documents provided in our GitHub repository. These scenarios highlight the AI's ability to detect dual-use risks and real-time geopolitical conflicts. 

1. Accessing the Terminal
App URL: https://ai.studio/apps/drive/1aXWc_iT28GnfTlH18m_XWnV5jRDAaDE-?fullscreenApplet=true

2. Preparing Test Assets
Download the two sample PDF documents from our GitHub Repository
(https://github.com/xiaoyi0217/sentinel-trade-terminal/tree/main/test-documents) :
a.Scenario1_Full_Realistic_Trade_Docs.pdf (Coffee Import)
b.Scenario2_Full_Realistic_Trade_Docs.pdf (Industrial Steel Import)

3. Scenario A: Multimodal Dual-Use Audit (Scenario 1)
This test demonstrates the AI’s ability to verify trade consistency using domain reasoning.
Action: In the Screening Terminal, upload Scenario1_Full_Realistic_Trade_Docs.pdf and click "Initiate Full Audit".

What to look for:
-Extraction: The AI identifies "Green Coffee Beans (Arabica)" with HS Code 0901.11.
-Thought Trace: Observe the Thought Trace panel. Gemini 3 Flash will verify that the beans are consistent with the buyer, Zuspresso (a coffee chain).
-The Result: It should return an APPROVE status with a Low Risk Index, confirming the transaction is logically sound.

4. Scenario B: Real-Time Sanctions Grounding (Scenario 2)
This test demonstrates Google Search Grounding against live events and identifying "out-of-character" cargo.
Action: Upload Scenario2_Full_Realistic_Trade_Docs.pdf and run the audit.

What to look for:
-Identification: The AI extracts the vessel MV South Ocean / V.88 and the cargo "SUS 304 Stainless Steel Sheets".
-Live Grounding: The model performs a live search for maritime enforcements, such as Operation Southern Spear.
-The Flag: It triggers a REJECT decision with a "Lack of Coherency" red flag. The AI reasons that industrial-grade steel (dual-use tech) is being shipped to a coffee chain, which is a high-risk inconsistency.

5. Verifying the Audit Trail
Action: Navigate to the Regulatory Vault tab.

What to look for:
-Evidence Hash: Locate the transaction you just processed. You will see a unique SHA-256 hash that cryptographically binds the AI's reasoning to the final decision, ensuring a tamper-proof audit trail for regulators.
