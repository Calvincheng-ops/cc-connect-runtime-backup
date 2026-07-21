# CC-Connect Runtime Backup

Private, secret-free reconstruction notes for the CC-Connect instance running on this Mac.

## Captured runtime

- Application: `cc-connect`
- Version: `v1.3.2`
- Upstream commit: `19406df9`
- Built: `2026-04-21T00:42:17Z`
- Installation method: global npm package
- Package path: `~/.local/lib/node_modules/cc-connect`
- Executable path: `~/.local/lib/node_modules/cc-connect/bin/cc-connect`
- Configuration directory: `~/.cc-connect`
- Service manager: macOS LaunchAgent (`com.cc-connect.service`)
- Log file: `/tmp/cc-connect.log`

The executable is intentionally not committed. It is a 20 MB platform-specific release artifact that can be restored from npm. Its checksum is recorded in `runtime/manifest.json`.

## Restore

1. Install the captured version:

   ```sh
   npm install -g cc-connect@1.3.2
   ```

2. Copy `config.example.toml` to `~/.cc-connect/config.toml`.
3. Replace every `REPLACE_ME` value locally. Never commit the completed file.
4. Adapt `service/com.cc-connect.service.plist.example` to the local username and npm installation path.
5. Install or reload the LaunchAgent using CC-Connect's daemon commands.

## Deliberately excluded

- API keys, tokens and platform credentials
- Real `config.toml`
- Session histories and chat content
- Weixin account state
- Cron/runtime state, PID and lock files
- Logs
- Downloaded executable

Upstream source and documentation: <https://github.com/chenhg5/cc-connect>

