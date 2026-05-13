# Skills SDK for Workshop

This SDK installs the [`skills`](https://www.npmjs.com/package/skills) npm
package into your workshop, providing the `npx skills` CLI for finding and
installing agent skills.

---

## Reference workshop

A minimal workshop:

```yaml
# workshop.yaml
name: agent-skills
base: ubuntu@24.04
sdks:
  - name: skills
    channel: latest/stable
```

This creates a basic skills environment with the `skills` CLI available.

---

## Using the SDK

### Prerequisites, project layout

1. No prerequisite SDKs are required.
2. Place your project files in your project directory. No special layout is
   required.

### Finding and installing skills

Inside the workshop, use the `skills` CLI to find and install skills.

```bash
# List globally installed skills
skills list --global

# Install a skill
skills install <skill-name>

# Search for skills
skills search <query>
```

Installed skills are stored in `/home/workshop/.agents/skills/` inside the
workshop.

---

## Plugs (resources this SDK consumes)

### skills

- Interface: `mount`
- Workshop target: `/home/workshop/.agents/skills`
- Purpose: Preserves the skills you have installed on your local system.
  You can also use `workshop remount` to control its contents on the host.
  To mount your existing `~/.agents/skills/` into the workshop, stop
  the workshop first, remount, then start it again:

  ```bash
  workshop stop <workshop-name>
  workshop remount <workshop-name>/skills:skills ~/.agents/skills
  workshop start <workshop-name>
  ```

## Slots (resources this SDK provides)

This SDK doesn't define any slots.

---

## Documentation and guidance

- [skills npm package](https://www.npmjs.com/package/skills)
- [Workshop documentation](https://canonical-workshop.readthedocs-hosted.com/latest/)

---

## Community and support

- Workshop forum:
  [Workshop Discourse](https://discourse.canonical.com/c/engineering/workshops/34)
- Please review our
  [Code of Conduct](https://ubuntu.com/community/ethos/code-of-conduct) before
  participating.

---

## Contributions

All contributions, including code, documentation updates, and issue reports,
are welcome!

- See `CONTRIBUTING.md` for guidelines.
- Open issues or pull requests on the official repository.

---

## License and copyright

Copyright 2026 Canonical Ltd.

This program is free software: you can redistribute it and/or modify it under
the terms of the
[GNU Lesser General Public License version 2.1 (LGPLv2.1)](https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html)
as published by the Free Software Foundation.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

The [`skills`](https://www.npmjs.com/package/skills) package is licensed under
the [MIT License](https://opensource.org/licenses/MIT).
