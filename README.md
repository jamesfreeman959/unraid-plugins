# Unraid plugins by jamesfreeman959

This repository is the [Community Applications](https://ca.unraid.net) feed for my Unraid plugins and Docker
templates. It only holds the listing metadata. Each app's code, issues and releases live in its own repository.

| Plugin | Repository | Support |
| --- | --- | --- |
| Disk Usage (duc) | [unraid-duc](https://github.com/jamesfreeman959/unraid-duc) | [Forum thread](https://forums.unraid.net/topic/200807-plugin-disk-usage-duc/) |

| Docker container | Repository | Support |
| --- | --- | --- |
| BorgWarehouse | [unraid-borgwarehouse](https://github.com/jamesfreeman959/unraid-borgwarehouse) | [Forum thread](https://forums.unraid.net/topic/200915-plugin-borgwarehouse/) |

To install, search for the app in the **Apps** tab of your Unraid server.

## Layout

| Path | Purpose |
| --- | --- |
| `ca_profile.xml` | Maintainer profile shown in Community Applications |
| `plugins/<name>.xml` | One wrapper per plugin. `<PluginURL>` must match the `pluginURL` in that plugin's `.plg` exactly |
| `templates/<name>.xml` | One Docker template per container. An exact copy of the template at its `<TemplateURL>` in the app's own repository |

## Adding a plugin

1. Publish the plugin from its own repository so that its `.plg` is reachable at a raw GitHub URL.
2. Copy `plugins/duc.xml` to `plugins/<name>.xml` and update every field. Set `<PluginURL>` to the `.plg` URL and
   `<Support>` to the plugin's forum thread.
3. Add the plugin to the table above and to the list in `ca_profile.xml`.
4. Push. The **Validate** workflow checks each wrapper's fields, fetches its `.plg` to confirm the URLs match,
   and checks that the icon and screenshot links work. It also runs weekly.
5. Run **Scan** for this repository at <https://ca.unraid.net/submit> so Community Applications picks up the new plugin.

## Adding a Docker container

Community Applications reads Docker templates from this feed directly, so the feed holds a full copy of each one.

1. Write and test the template in the app's own repository, with `<TemplateURL>` pointing at its raw GitHub URL there.
2. Copy it unchanged to `templates/<name>.xml`.
3. Add the container to the table above and to the list in `ca_profile.xml`.
4. Push. The **Validate** workflow checks the template's fields, that it is identical to the copy at its
   `<TemplateURL>`, and that its icon link works.
5. Run **Scan** at <https://ca.unraid.net/submit>.

To change a template later, edit it in the app's repository and copy it here again.

## License

MIT, see [LICENSE](LICENSE). Each app is covered by the license in its own repository.
