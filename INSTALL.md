# AI Safety Checker - Installation Guide

## For Users: How to Install This Skill

### Quick Install

1. **Download the skill files** (or clone from repository)
2. **In Claude, ask:**
   ```
   Please create the directory /mnt/skills/user/ai-safety-checker/
   ```

3. **Upload the files to Claude:**
   - Upload `SKILL.md`
   - Upload `evals/evals.json`
   - Upload `README.md` (optional)

4. **Ask Claude to install:**
   ```
   Please copy these uploaded files to /mnt/skills/user/ai-safety-checker/
   and create the evals subdirectory if needed.
   ```

5. **Verify installation:**
   ```
   Can you check if the ai-safety-checker skill is available?
   ```

### Manual Installation (via commands)

If you have the files, you can ask Claude to run:

```bash
# Create directory structure
mkdir -p /mnt/skills/user/ai-safety-checker/evals/files

# Copy files (Claude will do this for you)
# - SKILL.md → /mnt/skills/user/ai-safety-checker/
# - evals.json → /mnt/skills/user/ai-safety-checker/evals/
# - README.md → /mnt/skills/user/ai-safety-checker/
```

### Verify It's Working

Test the skill by asking Claude:

```
Review this code for safety issues:

@app.route('/kids-chat', methods=['POST'])
def kids_chatbot():
    message = request.json['message']
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": message}]
    )
    return response
```

Claude should identify this as CRITICAL and explain the children's safety issues.

## Repository Structure

```
ai-safety-checker/
├── SKILL.md              # Main skill file (REQUIRED)
├── README.md             # Documentation
├── CHANGELOG.md          # Version history
├── INSTALL.md            # This file
└── evals/
    ├── evals.json        # Test cases
    └── files/            # Supporting test files (empty for now)
```

## System Requirements

- Access to Claude (claude.ai or Claude API)
- Ability to upload files or paste text
- Computer use features enabled (for file operations)

## Troubleshooting

**Skill not triggering:**
- Verify files are in `/mnt/skills/user/ai-safety-checker/`
- Check that `SKILL.md` has proper YAML frontmatter
- Try explicitly mentioning "check for AI safety issues"

**Permission errors:**
- User skills go in `/mnt/skills/user/` (not `/mnt/skills/public/`)
- Ensure you're creating in the correct directory

**File upload issues:**
- Try uploading files one at a time
- Paste content directly if uploads fail
- Use bash commands to create files

## Updates

To update the skill:
1. Download the latest version
2. Replace existing files in `/mnt/skills/user/ai-safety-checker/`
3. Restart your conversation (or just continue)

## Support

For issues or questions:
- Check the README.md for usage guidance
- Review the CHANGELOG.md for recent changes
- Test with the evaluation cases in evals.json

## License

[Specify your license here - e.g., MIT, Apache 2.0, etc.]

## Credits

Created by: Mike
Based on research from: OWASP, EU AI Act, NIST AI RMF, academic papers on AI safety

## Contributing

If you want to improve this skill:
1. Test it thoroughly
2. Document issues or enhancements
3. Share improvements back with the community
