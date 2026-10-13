# X (Twitter) Agent Skills

11 free skills that turn Claude Code, Codex, Cursor or any skills-compatible
agent into an X (Twitter) content team. They write posts, threads, hooks and
replies in your voice, rebuild LinkedIn posts for X and back, fix your bio,
and check every draft against what X's own published ranking code rewards.

MIT licensed. No account, no API key, nothing phones home. Made by
[Liftli](https://liftli.ai/x?utm_source=github&utm_campaign=x-skills-readme).
Full directory with a card per skill:
[liftli.ai/x-agent-skills](https://liftli.ai/x-agent-skills/). For LinkedIn,
see the sibling set:
[liftli-ai/linkedin-agent-skills](https://github.com/liftli-ai/linkedin-agent-skills)
(31 skills).

## Install

**Any agent**, with the [skills](https://skills.sh) CLI:

```bash
npx skills add liftli-ai/x-agent-skills
```

**One skill:**

```bash
npx skills add liftli-ai/x-agent-skills --skill x-reply-generator
```

**Claude Code plugin** (all 11 skills):

```
/plugin marketplace add liftli-ai/x-agent-skills
/plugin install x-agent-skills@liftli-x
```

**By hand:** copy any folder under `skills/` into `~/.claude/skills/`, or
your agent's skills folder.

## Start here

1. Ask your agent: *"Help me with my X."* The `x-agent` skill picks the
   right skill for what you want.
2. Build your voice file. Say *"build my voice file"* and paste a few posts
   and replies you wrote. Every writing skill reads it, on X and on LinkedIn,
   so drafts sound like you. Template: [`templates/voice.md`](templates/voice.md).
3. Write, check with `x-algorithm-check`, then post.

## The skills

### Start

| Skill | What your agent gains |
|---|---|
| `x-agent` | The front door: routes any X request to the right skill and suggests a weekly routine |
| `x-voice` | Builds or updates the shared voice file (`.liftli/voice.md`), with a section for how you sound on X |
| `x-publish` | Gets a final post live: a copy-ready version to paste, or publishing through Liftli after you approve |

### Write

| Skill | What your agent gains |
|---|---|
| `x-post-writer` | Single posts: 280 characters counted X's way, or long posts up to 25,000 on Premium |
| `x-thread-writer` | Threads where post 1 stands alone and every post earns the next; says when one post is better |
| `x-hook-generator` | 8 first lines labeled by pattern, each checked for clarity, stakes and an open loop |
| `x-reply-generator` | Short, specific replies you post yourself, and the sourced reason replies are X's growth lever |
| `linkedin-to-x` | A LinkedIn post rebuilt for X: standalone, short thread, and long post |
| `x-to-linkedin` | An X post or thread expanded for LinkedIn, sized for the "see more" fold |

### Profile and checks

| Skill | What your agent gains |
|---|---|
| `x-bio-generator` | Bios within the 160-character limit, plus a name, pinned-post idea and header text |
| `x-algorithm-check` | A 12-point pre-publish check, each point tagged as backed by X's code or as craft |

## What the checks are based on

X has published its ranking code. The checks cite it instead of guessing:

- The 2026 For You algorithm:
  [xai-org/x-algorithm](https://github.com/xai-org/x-algorithm) (ranking
  weights in `home-mixer/params/param.rs`).
- The 2023 Heavy Ranker:
  [twitter/the-algorithm-ml](https://github.com/twitter/the-algorithm-ml/blob/main/projects/home/recap/README.md).
- Character counting:
  [twitter/twitter-text](https://github.com/twitter/twitter-text/blob/master/config/v3.json).
- Limits and rules: the X Help Center pages on
  [Premium longer posts](https://help.x.com/en/using-x/x-premium-how-to),
  [profiles](https://help.x.com/en/managing-your-account/how-to-customize-your-profile)
  and [automation](https://help.x.com/en/rules-and-policies/x-automation).

Anything not traceable to those sources is labeled as craft.

## What these skills don't do

They don't post, and no skill should. X's automation rules forbid scripting
the X website, and AI reply bots need X's prior written approval. So every
skill ends with copy-ready text you post yourself.

They also forget. Each chat starts from zero, apart from your voice file.

If you want your agent to publish and remember, that is what
[Liftli](https://liftli.ai/x?utm_source=github&utm_campaign=x-skills-readme)
does. It connects to the same agent as an MCP server, learns your voice from
your real posts, keeps your strategy between sessions, drafts from what you
actually did this week, and publishes or schedules posts and threads through
X's official API only after you approve each one. Free plan (first 3 posts),
no card. Publishing to X is on the Business plan.

```bash
claude mcp add --scope user --transport http liftli https://mcp.liftli.ai/mcp
claude mcp login liftli
```

Claude app, Codex, Cursor and other clients: [liftli.ai/llms.txt](https://liftli.ai/llms.txt).

## License

MIT. See [LICENSE](LICENSE).
