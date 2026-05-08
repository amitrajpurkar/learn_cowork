# Initializing Cowork or Claude Desktop Configuration


There are a bunch of markdown files that are meant to give instructions to AI Agent on what is expected of it and how it should behave

These files which are essentially supposed to be one time instructions are written in plain english
Claude or the AI Agent is expected to read these instructions at start of each session
these files in total equate into "TOKENS" 

the larger the token count, the more expensive the API call will be

## When Token Optimization IS Worth It
Yes, optimize aggressively if the file contains:

- Repetitive phrasing ("Always remember to...", "Please make sure that...")
- Verbose explanations of why rather than just what
- Full sentences where bullet fragments suffice
- Redundant examples that don't add new signal
- Prose-style instructions that can be compressed to structured directives

Ask Claude directly after pasting the file: "Optimize this for token efficiency while preserving all instructions. Use terse bullet format, remove redundant phrasing, no explanatory prose."

Convert above into a slash-command.
place a shell-script in the cowork directory that does this.

## knowing the token size of a file
Unit -- Typical Ratio for English text
1 byte -- 0.25 tokens
1 character -- 0.25 tokens
1 word -- 1.3 tokens
4 characters -- 1 token

 - Rough approximation: 1 token ≈ 4 chars for English markdown
 - to get character count: ```wc -m filename.md or wc -w -c filename.md```

 another way is to use below script
 ```
    python3 -c "
    import tiktoken
    enc = tiktoken.get_encoding('cl100k_base')
    with open('<filename>') as f:
        text = f.read()
    tokens = enc.encode(text)
    print(f'Bytes: {len(text.encode(\"utf-8\"))}')
    print(f'Tokens: {len(tokens)}')
    print(f'Ratio: {len(text.encode(\"utf-8\"))/len(tokens):.1f} bytes/token')
    "
```

## Date: May-8th-2026 -- Config Files for Claude

today i created two personas to use with Claude:
1. SWE - for general coding and development tasks
2. EE - for taking notes and organizing study materials

## Next steps for tomorrow
 - work on training videos from Anthropic's website
 - check few more infographics and videos