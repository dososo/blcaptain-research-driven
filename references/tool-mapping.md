# Cross-Platform Tool Mapping

Map capabilities, not habits. Confirm the active runtime inventory before relying on any exact name because clients and versions can wrap or rename tools.

Treat the names below as checked against official sources on 2026-07-11. Reconfirm them after material client upgrades.

## Use the Capability Matrix

| Capability | Claude Code | Codex | Gemini CLI |
|---|---|---|---|
| Search the web | `WebSearch` | `web_search`; enable live search for freshness-sensitive work | `google_web_search` |
| Open or read a webpage | `WebFetch` | Use `web_search` page-opening and in-page actions; no separate stable `web_fetch` tool is documented | `web_fetch` |
| Read local files | `Read`; use `Glob` or `Grep` to locate content | Use `exec_command` in the unified runtime or `shell_command` in legacy runtimes; confirm the exposed shell name | `read_file` or `read_many_files` |
| Delegate independent research | `Agent` | `spawn_agent`; use the available lifecycle controls to collect results | `invoke_agent` or an agent-name virtual tool |

## Claude Code

- Use `WebSearch` for current discovery.
- Use `WebFetch` to inspect the actual page.
- Use `Read` for local content; locate files with `Glob` or `Grep` when needed.
- Use `Agent` for independent sub-questions. Launch independent lines together when the runtime permits parallel calls.
- Prefer `Agent` over the older `Task` name. Treat `Task` as a compatibility alias, not the current name.
- Keep Claude Code's PascalCase names distinct from similarly named Claude API capabilities.

Verify names and behavior in the official [Claude Code tools reference](https://code.claude.com/docs/en/tools-reference) and [Claude Code subagents guide](https://code.claude.com/docs/en/sub-agents).

## Codex

- Use `web_search` for web discovery and page-opening actions.
- Enable live search for freshness-sensitive work. Do not treat cached search as arbitrary real-time page access.
- Do not invent a separate `web_fetch` or `read_file` tool for the base runtime.
- Use the exposed shell capability for local files. Prefer targeted commands such as `rg` and `sed` through `exec_command`; accept `shell_command` only when the runtime exposes the legacy path.
- Use `spawn_agent` for independent sub-questions. Use the available wait, message, resume, or close controls rather than assuming one fixed lifecycle interface across clients.
- Confirm network permissions before using a shell HTTP client for a direct URL that web search cannot open.

Verify current behavior in the official [Codex web search guide](https://developers.openai.com/codex/web-search), [Codex configuration reference](https://developers.openai.com/codex/config-file/config-reference), and [Codex subagents guide](https://developers.openai.com/codex/agent-configuration/subagents).

## Gemini CLI

- Use `google_web_search` for discovery.
- Use `web_fetch` to read identified URLs.
- Use `read_file` for one local file and `read_many_files` for a focused batch.
- Use `invoke_agent` when the runtime exposes the common agent invocation tool.
- Use a named virtual tool when Gemini exposes a specific agent by name. Treat `@agent_name` as routing syntax, not as the underlying function name.
- Launch independent agents together when the installed version supports parallel subagents.
- Fall back to sequential research when agent invocation is unavailable.
- Respect confirmation requirements and network boundaries when fetching URLs.

Verify names and behavior in the official [Gemini CLI tools reference](https://geminicli.com/docs/reference/tools/), [web search guide](https://geminicli.com/docs/tools/web-search/), [web fetch guide](https://geminicli.com/docs/tools/web-fetch/), [subagents guide](https://geminicli.com/docs/core/subagents/), and [`invoke_agent` implementation](https://github.com/google-gemini/gemini-cli/blob/f354eebaf43b25bacb176007e449bb9a638fd101/packages/core/src/agents/agent-tool.ts).

## Preserve the Method When Capabilities Differ

1. Confirm the runtime's available tools before planning calls.
2. Translate each need into a capability: discover, inspect, read locally, reproduce, or delegate.
3. Use the closest approved capability.
4. Run independent sub-questions in parallel only when they do not depend on one another.
5. Run the same work sequentially when delegation or parallel execution is unavailable.
6. Preserve source quality, active disconfirmation, certainty grading, and STOP conditions regardless of platform.
7. State any capability limitation that reduces coverage or certainty.
