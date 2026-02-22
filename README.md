# CrowdWisdomTrading AI Marketing Pipeline (n8n Workflow)

Automated marketing content generation pipeline using n8n + AI tools — created as part of the CrowdWisdomTrading internship assessment (Feb 2026).

### Overview
This workflow takes trader-themed product inputs (name + description) and generates:
- Catchy hooks and 15–20s ad scripts (Gemini)
- Brand logo/avatar & product images (Gemini)
- Professional voice-over (ElevenLabs)
- Talking avatar video (HeyGen)
- Logs results + saves assets to Google Drive / Sheets

Designed to be scalable (batches for 40+ products), production-ready (error handling, retries, documentation), and fully aligned with the assignment brief.

### Tech Stack
- **Orchestration**: n8n (self-hosted)
- **LLM & Image Gen**: Google Gemini (free tier)
- **Voice**: ElevenLabs (free tier)
- **Avatar & Video**: HeyGen (free tier — limited to 3 photo avatars)
- **Storage & Logging**: Google Drive + Google Sheets (OAuth)
- **Error Handling**: IF nodes, try-catch in Code nodes, logging

### Workflow Features
- Modular & documented (Sticky Notes on every node)
- Dynamic prompts using product data
- Asynchronous HeyGen avatar polling (waits for "success" status)
- Token/credit usage tracking
- Scalable batch processing

### Limitations (Free Tier)
- HeyGen photo avatar creation is limited to **3 lifetime** on free plan (even deleted avatars count).  
  → Video generation step uses stock avatars or requires paid plan for custom photo avatars.  
  → Polling loop is fully implemented and ready for unlimited quota.

### How to Run
1. Import `workflow.json` into n8n
2. Create credentials:
   - HeyGen: Header Auth → `xi-api-key`
   - ElevenLabs: Header Auth → `xi-api-key`
   - Google Gemini: Query Auth → `key`
   - Google Drive & Sheets: OAuth2
3. Add product input (name + description)
4. Execute workflow
5. Check Google Sheets for logs & Drive for assets

### Demo Video
https://drive.google.com/file/d/1q188UDLcityrdDBcKPW43vhcsXxY17o9/view?usp=sharing

### Notes for Evaluator
- Full custom photo avatar flow works on paid HeyGen plan.
- Happy to re-run end-to-end with provided API access / paid quota.
- Built & iterated ~100 workflow versions to reach this clean, robust version.

Thank you for the opportunity — excited to discuss how I can contribute to CrowdWisdomTrading's automation!

Ansh  
Mangaluru, Karnataka  
[Your Email] | [Your Phone] | [LinkedIn]
