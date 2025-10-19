# Product Management Coaching AI Agent

> Self-coaching tools and frameworks for Product Managers at every stage of their career journey

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Skills](https://img.shields.io/badge/Claude-Skills-purple)](https://www.anthropic.com/news/skills)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## 📖 Overview

This repository contains a comprehensive AI agent skill set designed to help Product Managers self-coach, develop their capabilities, and navigate their career journey. Built on Anthropic's Agent Skills framework, it provides tailored guidance across five PM archetypes and covers 10 essential skill areas.

**What This Is:**
- A self-coaching companion for Product Managers
- A structured framework for PM skill development
- An AI-powered guide to product management best practices
- A tool to help PMs navigate career transitions and challenges

**What This Is Not:**
- A replacement for human mentorship or professional coaching
- A commercial product or paid service
- A one-size-fits-all solution to all PM challenges
- A decision-making tool (it guides your thinking, doesn't decide for you)

## 🎯 Key Features

### Five PM Archetypes Covered
1. **Consumer PM** (The Craftsperson) - Design-focused, detail-oriented
2. **Growth PM** (The Data Scientist) - Metrics-driven, experiment-first
3. **GM PM** (The MBA) - Business model and market-focused
4. **Platform PM** (The Systems Thinker) - Building for builders
5. **Research PM** (The Algorithmic/AI PM) - Technical depth and rigor

### Ten Core Skills
1. PM Archetype Assessment & Coaching
2. Product Management Frameworks Navigator
3. Product Sense Development
4. Analytical & Execution Sense
5. Product Leadership & Team Management
6. Product Thinking & Problem Solving
7. Personal Growth & Meta-Skills
8. Strategic Communication & Influence
9. Continuous Learning & Growth
10. Product Management Superpowers

### 15+ Frameworks Included
- 3X Framework (Explore, Expand, Extract)
- Product Sense Interview Framework
- RICE & LNO Prioritization
- Jobs-to-be-Done (JTBD)
- North Star Metrics
- SHARED Feedback Model
- And many more...

## 🚀 Quick Start

### Prerequisites
- Claude Pro, Team, Max, or Enterprise subscription (for Claude.ai)
- OR Anthropic API access (for developers)
- OR Claude Code CLI (for command-line integration)

### Installation (Choose One)

#### Option A: Claude.ai (5 minutes)
```bash
1. Download pm-coaching-skills.md
2. Go to Claude.ai → Settings → Features
3. Enable "Skills"
4. Upload pm-coaching-skills.md as a custom skill
5. Start a new chat and try a sample prompt
```

#### Option B: Claude Code (15 minutes)
```bash
# See docs/CLAUDE_CODE_SETUP.md for detailed instructions
mkdir -p ~/.claude/skills/pm-coaching
cp pm-coaching-skills.md ~/.claude/skills/pm-coaching/SKILL.md
```

#### Option C: Claude API (30 minutes)
```bash
# See docs/API_SETUP.md for detailed instructions
curl https://api.anthropic.com/v1/skills \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "content-type: application/json" \
  -d @pm-coaching-skills.md
```

### Your First Coaching Session

Try this starter prompt:
```
Help me understand what type of Product Manager I am based on my natural 
tendencies and how I make decisions.
```

## 📁 Repository Structure

```
pm-coaching/
├── README.md                          # This file
├── LICENSE                            # MIT License
├── pm-coaching-skills.md              # Main skills file for AI agent
├── docs/
│   ├── SETUP_GUIDE.md                 # Detailed setup instructions
│   ├── SYSTEM_PROMPT.md               # System prompt configuration
│   ├── SAMPLE_PROMPTS.md              # Example prompts to get started
├── examples/
│   ├── archetype-assessment.md        # Example coaching session
│   ├── framework-selection.md         # Example prioritization help
│   ├── interview-prep.md              # Example interview coaching
│   ├── leadership-transition.md       # Example leadership guidance
│   └── cross-functional-influence.md  # Example influence coaching
└── CONTRIBUTING.md                    # How to contribute
```

## 💡 Use Cases

### For Individual Contributors
- Understand your PM archetype and natural strengths
- Learn which frameworks to use for different challenges
- Practice product sense and analytical thinking
- Prepare for PM interviews
- Navigate career transitions

### For Senior PMs & Leads
- Develop leadership capabilities
- Learn to coach and evaluate team members
- Master strategic communication
- Build cross-functional influence
- Transition from IC to management

### For Product Leaders
- Understand different PM archetypes on your team
- Apply appropriate coaching techniques
- Evaluate PM performance holistically
- Build high-performing product organizations
- Navigate organizational dynamics

## 📚 Documentation

- **[Setup Guide](docs/SETUP_GUIDE.md)** - Step-by-step installation for all platforms
- **[System Prompt](docs/SYSTEM_PROMPT.md)** - Configure your PM coaching agent
- **[Sample Prompts](docs/SAMPLE_PROMPTS.md)** - 5+ examples to get started


## 🎓 Learning Path

### Week 1: Self-Assessment
- Discover your PM archetype
- Identify strengths and growth areas
- Set development goals

### Week 2-4: Framework Mastery
- Learn prioritization frameworks
- Practice product sense methodology
- Apply analytical thinking

### Month 2-3: Leadership Development
- Develop strategic communication
- Build influence skills
- Practice coaching techniques

### Ongoing: Continuous Growth
- Monthly development reviews
- Framework application practice
- Career progression planning

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to suggest framework improvements
- Submitting new PM archetypes or skills
- Sharing coaching session examples
- Reporting issues or bugs

## ⚠️ Disclaimer

### Origins & Attribution
This PM coaching AI agent skill set has been developed through:
- **Personal Experience**: Years of practice as a Product Manager and Product Leader
- **Industry Knowledge**: Published materials and frameworks from thought leaders including:
  - [Shreyas Doshi](https://twitter.com/shreyas)
  - [Lenny Rachitsky](https://www.lennysnewsletter.com/)
  - [Marty Cagan](https://www.svpg.com/)
  - And many others in the PM community

### Intended Use
This tool is provided **free for personal, non-commercial use** to help Product Managers:
- Self-coach and develop their skills
- Navigate career challenges and transitions
- Learn and apply PM frameworks
- Prepare for interviews and promotions

### Important Limitations

**This AI Agent Is NOT:**
- ❌ A substitute for professional human coaching or mentorship
- ❌ A replacement for formal PM training programs
- ❌ Suitable for high-stakes business decisions without human oversight
- ❌ A guaranteed path to career success
- ❌ For commercial redistribution or resale

**This AI Agent IS:**
- ✅ A starting point for self-directed learning
- ✅ A framework reference and application guide
- ✅ A practice tool for developing PM thinking
- ✅ A complement to human mentorship and coaching
- ✅ Free to use and adapt for personal growth

### Recommendations
- **Seek Human Mentorship**: Use this tool alongside human coaches and mentors
- **Context Matters**: Adapt frameworks to your specific situation
- **Critical Thinking**: Question and validate AI suggestions
- **Continuous Learning**: Supplement with books, courses, and experience
- **Community Engagement**: Connect with other PMs for peer learning

### Legal
This project is licensed under the MIT License - see [LICENSE](LICENSE) file.

The frameworks and methodologies referenced are based on publicly available materials and industry best practices. All credit for original frameworks goes to their respective creators.

## 🙏 Acknowledgments

Special thanks to the Product Management community and thought leaders who have shared their knowledge openly:
- **Shreyas Doshi** - For the best product sense and nuanced product insights
- **Lenny Rachitsky** - For amazing community for PM, growth and career advice  
- **Marty Cagan** - For product leadership principles, organizational design and operating model
- **Anthropic** - For the Claude AI platform and Agent Skills framework
- **The PM Community** - For continuous sharing and collaboration

## 🗺️ Roadmap

### Current Version: 1.0
- ✅ Five PM archetypes
- ✅ Ten core skill areas
- ✅ 15+ frameworks
- ✅ Claude.ai, API, and Code support

### Planned Enhancements
- [ ] Industry-specific PM skills (B2B SaaS, Consumer, Platform, etc.)
- [ ] Advanced leadership scenarios
- [ ] AI/ML Product Management deep dive
- [ ] International PM context (cultural considerations)
- [ ] Community-contributed frameworks
- [ ] Video tutorials and examples

## ⭐ Show Your Support

If this project helps you in your PM journey:
- Star this repository
- Share with other PMs
- Contribute your own examples or improvements
- Provide feedback through issues or discussions

---

**Start Your PM Coaching Journey Today**

1. Download `pm-coaching-skills.md`
2. Follow the [Setup Guide](docs/SETUP_GUIDE.md)
3. Try your first prompt from [Sample Prompts](docs/SAMPLE_PROMPTS.md)
4. Share your success story!

---

*Built with ❤️ for the Product Management community*

*Last Updated: October 2025 | Version 1.0*