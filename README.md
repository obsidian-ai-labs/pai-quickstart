# PAI Quickstart

Get PAI (Personal AI Infrastructure) installed on your machine in about 15 minutes. Run it yourself; we can help if you'd rather not.

This is the install path for the Claude-Code-based PAI substrate — the same architecture Obsidian AI Labs runs to operate our entire business. Five named agents, signed inter-agent messaging across hosts, persistent memory, voice cloning, the works.

If you'd rather run a fully local, container-based stack with Ollama (no cloud API calls), see the sister project: **[openclaw-quickstart](https://github.com/obsidian-ai-labs/openclaw-quickstart)**. Same install-yourself philosophy, different architecture.

## What you'll have when this finishes

A working PAI baseline on your Mac:

- `~/.claude/` directory tree with the PAI conventions
- Claude Code installed and running
- All the system-level tools (bun, git, ffmpeg, yt-dlp, ripgrep, jq, gh, node 22) the more advanced workflows need
- A bootstrap `CLAUDE.md` you customize as you go
- An empty `PAI/USER/ABOUTME.md` template waiting for your details
- A foundation we can build your industry-specific agents on top of

What you WON'T have on day one:

- A pre-configured agent fleet for your business — that gets wired in either by you (using the patterns this repo exposes) or by us
- Any of our production data, memory, clients, or skills — clean slate by design

## Who this is for

Three types of people:

1. **Technical operators** who want to try PAI themselves before buying anything. You can do the entire install + first session in an evening.
2. **Curious developers** who've read about agent fleets and want to see what one actually looks like in practice.
3. **Small business owners working with us.** When you engage Obsidian AI Labs to install or build your agent fleet, this is the foundation we put on your hardware before we wire in your custom agents.

## Prerequisites

- A Mac (Apple Silicon M1/M2/M3/M4 strongly preferred; Intel works but slower)
- macOS 13 (Ventura) or newer
- About 5 GB of free disk space
- An [Anthropic account](https://console.anthropic.com) for Claude API access (this is our referral link — it helps us a little, no cost to you)
- Optional: OpenAI account for Whisper transcription
- Optional: ElevenLabs account for voice features

## Install

### Path A: one-liner from this repo

Open Terminal and paste:

```bash
curl -fsSL https://raw.githubusercontent.com/obsidian-ai-labs/pai-quickstart/main/install.sh | bash
```

The script will:

1. Install Homebrew if you don't have it (asks for your password)
2. Install `bun`, `git`, `ffmpeg`, `yt-dlp`, `gh`, `jq`, `ripgrep`, `node@22` via Homebrew
3. Install Claude Code CLI globally
4. Scaffold `~/.claude/` with the PAI baseline directory tree
5. Drop a `.env.template` you fill in with your own keys
6. Create a minimal `CLAUDE.md` you customize as you go
7. Print next-step instructions

Safe to re-run. Skips anything you already have. Stops and tells you exactly what failed if anything goes wrong.

Expected runtime: 10-15 minutes on a fresh Mac, mostly waiting for Homebrew downloads.

### Path B: clone and run

If you'd rather inspect the script before running it (good instinct):

```bash
git clone https://github.com/obsidian-ai-labs/pai-quickstart.git ~/pai-quickstart
cd ~/pai-quickstart
less install.sh         # read it
./install.sh            # run it
```

## What to do after the script finishes

```bash
# 1. Copy the env template and fill in your keys
cp ~/.claude/.env.template ~/.claude/.env
open -e ~/.claude/.env

# 2. Fill in PAI/USER/ABOUTME.md with your real info
open -e ~/.claude/PAI/USER/ABOUTME.md

# 3. Launch Claude Code
cd ~/.claude && claude

# 4. When prompted "Allow this folder?", type 1 and press Enter

# 5. Test it by asking: "What's in this directory?"
```

If Claude Code answers with a real read of the directory, you're up.

## What happens next (if you keep going)

The install gives you the foundation. The interesting layer is what you build on top of it. Three directions people go:

**Direction 1 — Personal operator.** You spend a weekend writing your `CLAUDE.md`, customizing your skills, creating a personal `Telegram` agent you can reach from anywhere. Maybe a week later you've got it running your calendar and your morning research. This is the slow, sustainable path.

**Direction 2 — Single business focus.** You're a real estate agent, a clinic owner, a consultant. You wire one specific agent to one specific workflow that's eating your time. Paperwork generation. Client intake. Daily research. The PAI substrate underneath supports it, but you only build the one agent that pays for itself first.

**Direction 3 — Full agent fleet.** Multiple named agents, signed inter-agent messaging across separate hosts, the full setup we run. This is a several-week project of disciplined building. We can help if you want to skip the learning curve.

## Want help

If you'd rather have us install and tune this for you, or build out the agent fleet that fits your business specifically, reach out at info@obsidianailabs.ca or visit [obsidianailabs.ca](https://obsidianailabs.ca).

## Trust signals

- MIT licensed. Everything in this repo, you can fork and modify.
- Zero telemetry. We don't phone home from this installer or the resulting `~/.claude/` setup.
- The team behind this runs PAI for our own business. We're not selling something we don't use.

## Questions

Open an issue here. We watch this repo and reply.

## License

MIT. See [LICENSE](LICENSE).
