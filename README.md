# Drupal Agent Skills

Use [drupal-contribution-workflow](skills/drupal-contribution-workflow/SKILL.md) to take a Drupal issue from an agreed change to a tested merge request. The skill helps contributors find existing work, choose the correct issue fork, and give reviewers the evidence they need. Maintainers can also use it to verify the reviewed revision, the squash commit message, and contribution credit.

This is a community resource maintained by Pixie Works. Each Drupal project sets its own contribution and review practices.

## Try it

Start with a project and issue you already know. For example, open your local checkout and ask:

> Use drupal-contribution-workflow with this issue URL: <issue-url>. Read the discussion, identify the target branch and any existing MR, and suggest how to test the requested change. Stop after the plan.

For an implementation request, describe the expected result and your role. A contributor's handoff includes the tested commit, the CI result, and any questions still open for the maintainer. Keep your account choices, approval channel, and test environment in your own configuration.

## Install in Codex or Claude Code

Clone this repository into a location you intend to keep. From its root, run the block for your agent once. These commands assume a new installation on macOS or Linux.

```sh
git clone https://github.com/pixieworksinc/drupal-agent-skills.git
cd drupal-agent-skills
```

**Codex**

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD/skills/drupal-contribution-workflow" "$HOME/.agents/skills/"
```

Start a new session and select `$drupal-contribution-workflow`. See [Codex skills](https://developers.openai.com/codex/skills/).

**Claude Code**

```sh
mkdir -p "$HOME/.claude/skills"
ln -s "$PWD/skills/drupal-contribution-workflow" "$HOME/.claude/skills/"
```

Start a new session and use `/drupal-contribution-workflow`. See [Claude Code skills](https://code.claude.com/docs/en/skills).

The links point to the same Markdown file in your checkout. To update, review upstream changes and run `git pull --ff-only` there. Other [Agent Skills](https://agentskills.io/specification) clients can use the same skill directory.

## Using the skill on a Drupal project

The contributor verifies the proposed change, runs the relevant tests, and takes responsibility for what they submit. Follow the target project's instructions and Drupal's policies on [AI-assisted contributions](https://www.drupal.org/docs/develop/issues/issue-procedures-and-etiquette/policy-on-the-use-of-ai-when-contributing-to-drupal) and [automated access](https://www.drupal.org/drupalorg/docs/apis/use-of-automation-tools-including-ai). You can use the skill with a local checkout and submit the contribution yourself.
