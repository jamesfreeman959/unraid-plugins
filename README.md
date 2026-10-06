# Unraid plugins by jamesfreeman959

This repository is the [Community Applications](https://ca.unraid.net) feed for my Unraid plugins. It only holds
the listing metadata. Each plugin's code, issues and releases live in its own repository.

| Plugin | Repository | Support |
| --- | --- | --- |
| Disk Usage (duc) | [unraid-duc](https://github.com/jamesfreeman959/unraid-duc) | [Forum thread](https://forums.unraid.net/topic/200807-plugin-disk-usage-duc/) |

To install, search for the plugin in the **Apps** tab of your Unraid server.

## Layout

| Path | Purpose |
| --- | --- |
| `ca_profile.xml` | Maintainer profile shown in Community Applications |
| `plugins/<name>.xml` | One wrapper per plugin. `<PluginURL>` must match the `pluginURL` in that plugin's `.plg` exactly |

## Adding a plugin

1. Publish the plugin from its own repository so that its `.plg` is reachable at a raw GitHub URL.
2. Copy `plugins/duc.xml` to `plugins/<name>.xml` and update every field. Set `<PluginURL>` to the `.plg` URL and
   `<Support>` to the plugin's forum thread.
3. Add the plugin to the table above and to the list in `ca_profile.xml`.
4. Push. The **Validate** workflow checks each wrapper's fields, fetches its `.plg` to confirm the URLs match,
   and checks that the icon and screenshot links work. It also runs weekly.
5. Run **Scan** for this repository at <https://ca.unraid.net/submit> so Community Applications picks up the new plugin.

## License

MIT, see [LICENSE](LICENSE). Each plugin is covered by the license in its own repository.
