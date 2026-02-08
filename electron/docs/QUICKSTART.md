# Quick Start Guide

## 1. Installation (5 minutes)

### Requirements

- Node.js 16+ ([Download](https://nodejs.org))
- Python 3.8+ ([Download](https://www.python.org))
- OpenAI API Key ([Get Key](https://platform.openai.com/api-keys))

### Setup

```bash
# Clone or download the app
cd subtitle-translator

# Install dependencies
npm install
pip install -r requirements.txt
```

## 2. First Translation (10 minutes)

### Step 1: Prepare Files

1. Create a folder with your SRT files (e.g., `translations/input/`)
2. Create an output folder (e.g., `translations/output/`)
3. **Note**: SRT files should be named like `episode_01_EN.srt`

### Step 2: Start App

```bash
npm start
```

### Step 3: Configure

1. **API Key**: Enter your OpenAI API key
   - Get from https://platform.openai.com/api-keys
   - Starts with `sk-proj-`
2. **Source Folder**: Select input folder with SRT files
3. **Output Folder**: Select output folder for translations
4. **Languages**: Choose target languages (e.g., Hinglish, Taglish)
5. **Model**: Select GPT model (gpt-4o-mini = fastest & cheapest)

### Step 4: Review Estimate

- App shows token count and estimated cost
- Verify cost before proceeding

### Step 5: Start Translation

- Click "Start Translation"
- Monitor progress bar
- Wait for "Validation complete" message

### Step 6: Review Results

- Check validation results
- If all files pass: ✅ Done!
- If some fail: ⚠️ Retranslate them
- Click "Retranslate Failed Files"

## 3. Understanding the Interface

### Left Panel

**API Configuration**

- Enter your OpenAI API key
- Auto-saved securely

**Model Selection**

- **gpt-4o-mini**: Fastest & cheapest (recommended)
- **gpt-4o**: Higher quality
- **gpt-5-mini**: Balanced
- **gpt-5**: Premium quality

**Translation Mode**

- **Parallel Languages**: All languages per file simultaneously
- **Parallel Files**: Multiple files at same time
- Both enabled = Maximum speed

**Folders**

- **Source Folder**: Where your SRT files are
- **Output Folder**: Where translations go

### Right Panel

**Target Languages**

- Select languages you want to translate to
- Shows flag emoji for each language
- Use "Select All" / "Clear" buttons

**Translation Progress**

- Live progress bar (0-100%)
- Real-time status updates

**Status**

- Shows current action or error
- Updates every step

**Action Buttons**

- **Start Translation**: Begin translation process
- **Retranslate Failed Files**: Retry failed translations
- **Cancel Translation**: Stop current translation

## 4. Error Handling

### If Translation Fails

**See error in UI** → Click "Retranslate Failed Files" → Wait for retry

**See API key error** → Check API key → Re-enter in Settings → Try again

**See file error** → Check source folder exists → Verify SRT format → Try again

### Check Error Log

```bash
# View errors (Linux/Mac)
cat python/logs/translation_errors.log

# View errors (Windows PowerShell)
Get-Content python/logs/translation_errors.log
```

## 5. Tips & Tricks

### ✅ DO

- ✅ Start with one file to test
- ✅ Use parallel modes for multiple files
- ✅ Use gpt-4o-mini for cost savings
- ✅ Keep app window in focus
- ✅ Check validation results

### ❌ DON'T

- ❌ Close app during translation
- ❌ Use invalid SRT format
- ❌ Exceed API quota
- ❌ Use multiple API keys simultaneously
- ❌ Ignore validation warnings

## 6. Output Files

### File Structure

```
output/
├── Hinglish/
│   ├── episode_01_HI.srt
│   └── episode_02_HI.srt
├── Taglish/
│   ├── episode_01_TL.srt
│   └── episode_02_TL.srt
└── Vietnamese/
    ├── episode_01_VI.srt
    └── episode_02_VI.srt
```

### File Naming

- Format: `{original_name}_{language_code}.srt`
- Example: `episode_01_EN.srt` → `episode_01_HI.srt`
- Language codes: HI, TL, VI, TH, MS, ES, ID

## 7. Cost Examples

### Typical Costs (gpt-4o-mini)

- **1 episode (50 blocks)**: ~$0.01-0.05
- **10 episodes (500 blocks)**: ~$0.10-0.50
- **100 episodes (5000 blocks)**: ~$1.00-5.00

_Costs vary based on content length and language_

### Budget Tips

1. Use gpt-4o-mini (cheapest)
2. Translate one language at a time (if budget limited)
3. Monitor token count before translating
4. Use parallel processing (doesn't increase tokens)

## 8. Troubleshooting

| Issue                  | Solution                                              |
| ---------------------- | ----------------------------------------------------- |
| "API Key Invalid"      | Get new key from https://platform.openai.com/api-keys |
| "No SRT Files Found"   | Check source folder path, verify files end in .srt    |
| "Permission Denied"    | Check output folder permissions, try different folder |
| "Translation Timeout"  | Check internet connection, try again later            |
| "Block Count Mismatch" | Retranslate file (common for long content)            |

## 9. Getting Help

1. **Check Error Display**: UI shows descriptive error messages
2. **Check Error Log**: `python/logs/translation_errors.log`
3. **Read Docs**: See `PRODUCTION_README.md` for full guide
4. **Review Examples**: All language prompts include examples
5. **Test First**: Use test file before full batch

## 10. Advanced Usage

### Command Line (Dev Mode)

```bash
# Run with DevTools open
npm run dev

# Build for distribution
npm run build:win  # Windows
npm run build:mac  # macOS
npm run build:linux # Linux
```

### Run Tests

```bash
python python/test_suite.py
```

### Check Python Version

```bash
python --version  # Should be 3.8+
pip --version
```

---

**Need More Help?** See `ERROR_REFERENCE.md` for comprehensive error guide.

**Ready to Translate?** Start the app with `npm start` 🚀
