# Setup Guide - PM Coaching AI Agent

Complete installation instructions for all platforms.

## 📋 Prerequisites

Before you begin, ensure you have one of the following:

- **Claude.ai**: Pro, Team, Max, or Enterprise subscription
- **Claude API**: Anthropic API key and account
- **Claude Code**: CLI tool installed

## 🎯 Choose Your Platform

Click on your preferred platform for detailed setup instructions:

| Platform | Best For | Setup Time | Difficulty |
|----------|----------|------------|------------|
| [Claude.ai](#option-a-claudeai-setup) | Individual PMs | 5 minutes | ⭐ Easy |
| [Claude Code](#option-c-claude-code-setup) | Developer Workflows | 15 minutes | ⭐⭐ Intermediate |
| [Claude API](#option-b-claude-api-setup) | Developers, Custom Apps | 30 minutes | ⭐⭐⭐ Advanced |


---

## Option A: Claude.ai Setup

**Perfect for**: Individual PMs who want to start coaching immediately

### Step 1: Download the Skills File

1. Navigate to the repository: `github.com/pateltoc/pm-coaching`
2. Click on `pm-coaching-skills.md`
3. Click the **Download** or **Raw** button
4. Save the file to your computer (keep the `.md` extension)

### Step 2: Enable Skills in Claude.ai

1. Go to [claude.ai](https://claude.ai)
2. Log in to your account
3. Click your **profile icon** (bottom left)
4. Select **Settings**
5. Navigate to **Features** tab
6. Find **"Skills"** and toggle it **ON**

> **Note for Team/Enterprise Users**: Your admin must first enable Skills organization-wide. Contact your admin if you don't see the Skills option.

### Step 3: Upload the PM Coaching Skill

1. Start a **new conversation** in Claude
2. Look for the **Skills icon** (briefcase/toolbox icon) in the chat interface
3. Click **"Upload Custom Skill"** or **"Add Skill"**
4. Select the `pm-coaching-skills.md` file you downloaded
5. Wait for upload confirmation (should take 5-10 seconds)

### Step 4: Verify Installation

Test that the skill is working by starting a new conversation and typing:

```
What PM coaching skills do you have available?
```

**Expected Response**: Claude should reference the PM coaching skills and mention the five archetypes (Consumer, Growth, GM, Platform, Research PMs).

If Claude doesn't reference the skills:
- Verify the skill is uploaded in Settings → Skills
- Try starting a fresh conversation
- Make sure Skills are enabled in Features

### Step 5: Configure Custom Instructions (Optional but Recommended)

To get better coaching responses, add the system prompt to your Custom Instructions:

1. Go to **Settings** → **Custom Instructions**
2. Copy the system prompt from [docs/SYSTEM_PROMPT.md](SYSTEM_PROMPT.md)
3. Paste into the **Custom Instructions** field
4. Click **Save**

### Step 6: Start Your First Coaching Session

Try one of these starter prompts from [docs/SAMPLE_PROMPTS.md](SAMPLE_PROMPTS.md):

```
Help me understand what type of Product Manager I am based on my 
natural tendencies and how I make decisions.
```

🎉 **You're all set!** Start exploring the coaching capabilities.

---

## Option B: Claude Code Setup

**Perfect for**: Developers who want PM coaching integrated into their coding workflow

### Prerequisites

- Claude Code CLI installed ([installation guide](https://docs.claude.com/claude-code))
- Terminal/command line access
- Basic familiarity with command line tools

### Step 1: Install Claude Code (if not already installed)

Follow the official installation guide:
```bash
# Installation instructions at https://docs.claude.com/claude-code
```

Verify installation:
```bash
claude --version
```

### Step 2: Create Skills Directory

```bash
# Create the skills directory structure
mkdir -p ~/.claude/skills/pm-coaching
```

### Step 3: Copy the Skills File

```bash
# Navigate to where you downloaded pm-coaching-skills.md
cd ~/Downloads  # or wherever you saved the file

# Copy to Claude Code skills directory
cp pm-coaching-skills.md ~/.claude/skills/pm-coaching/SKILL.md
```

**Important**: The file MUST be named `SKILL.md` (all caps) in the skill directory.

### Step 4: Verify Installation

```bash
# List all installed skills
claude skills list
```

**Expected Output**: Should show `pm-coaching` in the list of available skills.

### Step 5: Test the Skill

Create a test project and use the skill:

```bash
# Start Claude Code
claude

# In Claude, try:
# "Use the pm-coaching skill to help me understand my PM archetype"
```

### Step 6: Use in Projects

The skill will automatically be available in Claude Code when relevant. You can also explicitly invoke it:

```bash
# In any Claude Code session
"Using PM coaching skills, help me prioritize these features..."
```

### Installing from Marketplace (Alternative)

If this skill becomes available in the Claude Code marketplace:

```bash
# Search for the skill
claude skills search pm-coaching

# Install from marketplace
claude skills install pm-coaching
```

### Updating the Skill

When updates are released:

```bash
# Remove old version
rm ~/.claude/skills/pm-coaching/SKILL.md

# Copy new version
cp pm-coaching-skills.md ~/.claude/skills/pm-coaching/SKILL.md

# Restart Claude Code
```

---

## Option C: Claude API Setup

**Perfect for**: Developers building custom PM coaching tools or team deployments

### Prerequisites

- Anthropic API key ([get one here](https://console.anthropic.com/))
- Python 3.8+ or Node.js 16+ installed
- Basic programming knowledge
- Terminal/command line access

### Step 1: Install Required Packages

#### For Python:
```bash
pip install anthropic
```

#### For Node.js:
```bash
npm install @anthropic-ai/sdk
```

### Step 2: Set Up Your API Key

#### For macOS/Linux:
```bash
export ANTHROPIC_API_KEY='your-api-key-here'
```

#### For Windows (Command Prompt):
```bash
set ANTHROPIC_API_KEY=your-api-key-here
```

#### For Windows (PowerShell):
```bash
$env:ANTHROPIC_API_KEY='your-api-key-here'
```

### Step 3: Upload the Skill via API

#### Option 3a: Using cURL (All Platforms)

```bash
curl https://api.anthropic.com/v1/skills \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "content-type: application/json" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: code-execution-2025-08-25,files-api-2025-04-14" \
  -F "name=pm-coaching-skills" \
  -F "description=Comprehensive PM coaching across all archetypes" \
  -F "file=@pm-coaching-skills.md"
```

#### Option 3b: Using Python

```python
import anthropic
import os

# Initialize the client
client = anthropic.Anthropic(
    api_key=os.environ.get("ANTHROPIC_API_KEY")
)

# Upload the skill
with open('pm-coaching-skills.md', 'rb') as f:
    skill = client.skills.create(
        name="pm-coaching-skills",
        description="Comprehensive PM coaching across all archetypes",
        file=f
    )

print(f"Skill uploaded successfully! ID: {skill.id}")
```

#### Option 3c: Using Node.js

```javascript
import Anthropic from '@anthropic-ai/sdk';
import fs from 'fs';

const client = new Anthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
});

async function uploadSkill() {
  const fileContent = fs.readFileSync('pm-coaching-skills.md');
  
  const skill = await client.skills.create({
    name: 'pm-coaching-skills',
    description: 'Comprehensive PM coaching across all archetypes',
    file: fileContent,
  });
  
  console.log('Skill uploaded successfully! ID:', skill.id);
  return skill.id;
}

uploadSkill();
```

### Step 4: Use the Skill in API Calls

#### Python Example:

```python
import anthropic

client = anthropic.Anthropic()

# Create a message with the PM coaching skill
message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=4096,
    tools=[
        {
            "type": "code_execution",
            "container": {
                "type": "skills",
                "skill_ids": ["pm-coaching-skills"]  # Use your skill ID
            }
        }
    ],
    messages=[{
        "role": "user",
        "content": "Help me understand what type of Product Manager I am."
    }]
)

print(message.content)
```

#### Node.js Example:

```javascript
const message = await client.messages.create({
  model: 'claude-sonnet-4-5-20250929',
  max_tokens: 4096,
  tools: [{
    type: 'code_execution',
    container: {
      type: 'skills',
      skill_ids: ['pm-coaching-skills']  // Use your skill ID
    }
  }],
  messages: [{
    role: 'user',
    content: 'Help me understand what type of Product Manager I am.'
  }]
});

console.log(message.content);
```

### Step 5: Add System Prompt

For best results, include the system prompt in your API calls:

```python
# Load system prompt from file
with open('docs/SYSTEM_PROMPT.md', 'r') as f:
    system_prompt = f.read()

message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=4096,
    system=system_prompt,  # Add system prompt here
    tools=[{
        "type": "code_execution",
        "container": {
            "type": "skills",
            "skill_ids": ["pm-coaching-skills"]
        }
    }],
    messages=[{
        "role": "user",
        "content": "Help me understand what type of Product Manager I am."
    }]
)
```

### Step 6: Verify Installation

Run a test query to confirm everything works:

```python
# Test script
test_message = client.messages.create(
    model="claude-sonnet-4-5-20250929",
    max_tokens=1024,
    tools=[{"type": "code_execution", "container": {"type": "skills", "skill_ids": ["pm-coaching-skills"]}}],
    messages=[{"role": "user", "content": "List the five PM archetypes you can coach."}]
)

print(test_message.content)
```

**Expected Output**: Should list Consumer PM, Growth PM, GM PM, Platform PM, and Research PM.

### Additional Resources

- [Full API documentation](API_SETUP.md)
- [Anthropic API Reference](https://docs.anthropic.com/en/api/messages)
- [Code examples repository](../examples/)


---

## 🔍 Verification Checklist

After setup on any platform, verify the following:

- [ ] Skill is uploaded/installed successfully
- [ ] Test prompt returns relevant PM coaching response
- [ ] Agent references the five PM archetypes
- [ ] Framework recommendations are specific and actionable
- [ ] System prompt is configured (if applicable)

## ❓ Common Issues

### Issue: "Skills not enabled"
**Solution**: 
- For Claude.ai: Check Settings → Features → Skills (toggle ON)
- For Team/Enterprise: Contact admin to enable organization-wide

### Issue: "Skill not loading in conversations"
**Solution**:
- Start a fresh conversation
- Explicitly mention the skill: "Using PM coaching skills..."
- Verify upload in Settings → Skills

### Issue: "API returns error about beta features"
**Solution**:
- Ensure you have the required beta headers:
  - `code-execution-2025-08-25`
  - `files-api-2025-04-14`

### Issue: "Responses don't seem tailored to PM coaching"
**Solution**:
- Add the system prompt (see [SYSTEM_PROMPT.md](SYSTEM_PROMPT.md))
- Be more specific in your prompts
- Reference your archetype or specific framework needs

### Issue: "Skill file won't upload"
**Solution**:
- Verify file is `.md` format
- Check file size (should be under 5MB)
- Ensure no special characters in filename
- Try downloading again from GitHub

---

## 🎓 Next Steps

After successful setup:

1. **Read [SAMPLE_PROMPTS.md](SAMPLE_PROMPTS.md)** - Try example prompts
2. **Review [FRAMEWORKS_REFERENCE.md](FRAMEWORKS_REFERENCE.md)** - Quick framework lookup
3. **Start Coaching** - Begin with archetype assessment
4. **Explore Examples** - Check out real coaching sessions in `/examples`
5. **Join Community** - Share your experience in [Discussions](https://github.com/pateltoc/pm-coaching/discussions)

---

## 📞 Need Help?

- **Setup Issues**: [Open an issue](https://github.com/pateltoc/pm-coaching/issues) with tag `setup-help`
- **General Questions**: [GitHub Discussions](https://github.com/pateltoc/pm-coaching/discussions)
- **Bug Reports**: [Report a bug](https://github.com/pateltoc/pm-coaching/issues/new?template=bug_report.md)

---

*Setup guide last updated: October 2025*