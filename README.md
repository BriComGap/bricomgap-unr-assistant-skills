# UNR Skills

Ask sourced questions about the University of Freiburg's Faculty of Environment and Natural Resources (UNR; Fakultät für Umwelt und Natürliche Ressourcen). The **UNR Assistant** plugin contains one `unr-assistant` skill and a connection to [UNR Knowledge](https://mcp.bricomgap.uni-freiburg.de/mcp), the MCP server. It covers people, teaching, administration, research, publications, projects, media coverage, and scientific paper content.

You do not need to download the repository or install a local server. Install the plugin for your app, then check that its UNR Knowledge connector is available. The server provides the live sources; the skill helps the assistant choose and interpret them.

## Codex desktop

The easiest way is to paste this into a Codex chat:

> Install the UNR Assistant plugin from https://github.com/BriComGap/unr-assistant-skills for my account. Add its UNR Marketplace, install the plugin and its bundled UNR Knowledge MCP connection, and verify that the server offers `search_faculty_website` and `publications_query`. If an app setting needs my click, tell me exactly where to click.

If you prefer to do the setup yourself, add the repository as a marketplace with `codex plugin marketplace add BriComGap/unr-assistant-skills`. In the Codex Plugins Directory, select **UNR Marketplace** (`unr-marketplace`) and install **UNR Assistant** (`unr-assistant`). Start a new chat if the skill or tools do not appear in the current one.

If you installed an earlier release, the renamed marketplace and plugin may appear as new entries. Remove the earlier entries in your app's plugin settings before installing this version.

## Claude Desktop

1. Open **Customize → Plugins → Add → Add marketplace**.
2. Enter `https://github.com/BriComGap/unr-assistant-skills` and add the marketplace.
3. Select **UNR Assistant** (`unr-assistant`) and click **Add**.
4. Open the plugin's **Connectors** tab and **Add** or **Connect** UNR Knowledge if prompted. In a Team or Enterprise organization, an owner may need to add the connector first.
5. In a chat, use the **+ → Connectors** menu to enable it if necessary.

Claude plugins require a paid Claude plan. On a Free plan, you can instead add `https://mcp.bricomgap.uni-freiburg.de/mcp` under **Customize → Connectors → Add custom connector**, and upload the [skill ZIP](dist/unr-assistant-skill.zip) under **Customize → Skills**. Those are two separate setup steps.

## Try it

Ask a question such as **“Wo lehrt Heiner Schanz?”** or **“What methods do the available UNR papers use to study forest biodiversity?”**. The assistant should call the UNR Knowledge tools and cite returned sources. You can invoke the skill explicitly with `$unr-assistant` in Codex or `/unr-assistant:unr-assistant` in Claude.

If the tools are unavailable, check that the plugin is enabled, the connector is connected, and the chat has access to it. Installing only the skill text does not connect the server. GitHub installation for other users requires a public repository or authorized access to a private one.

## Repository contents

- `plugins/unr-assistant/`: the installable plugin, skill, and MCP configuration.
- `.claude-plugin/marketplace.json`: the GitHub marketplace catalog used by Claude and supported by Codex.
- `docs/dev/`: earlier drafts and source material used to write the skill.

The plugin is released under the [MIT License](LICENSE). The remote server and the material it retrieves may have separate terms.

Installation references: [Codex plugin marketplaces](https://developers.openai.com/plugins/build/plugins) and [Claude plugins](https://claude.com/docs/plugins/overview).
