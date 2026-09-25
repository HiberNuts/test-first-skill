# Test First

An agent skill for writing useful tests before changing behavior. It prompts the agent to identify relevant success and failure cases, prove the tests fail for the right reason, and use mocks at external boundaries when needed. It also discourages duplicate tests and assertions about implementation details.

## Install in Codex

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/HiberNuts/test-first-skill.git ~/.agents/skills/test-first
```

Codex can select the skill for matching coding tasks. To request it explicitly, include `$test-first` in your prompt. For a single repository, clone it under that repository's `.agents/skills/test-first` instead.

See [Codex skill locations](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills) for other installation options.

## License

MIT. See [LICENSE](LICENSE).
