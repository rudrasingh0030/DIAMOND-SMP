# DIAMOND-SMP

A small private Eaglercraft survival server project.

## Planned server

- Minecraft/Paper: 1.12.2
- Client: Eaglercraft 1.12.2
- Game mode: Survival
- Difficulty: Normal
- Keep inventory: **off** (Minecraft default)
- Player access: whitelist enabled
- Authentication: LoginSecurity plugin

## Hosting notes

This repository includes a Render Blueprint for a **free test deployment**. It is not a guarantee of an always-online server.

Important limitations of the free plan:
- The service can sleep when idle and take time to wake up.
- The free service has no persistent disk in this configuration. World data, player progress, and plugin data may be lost after a restart, redeploy, or suspension.
- The low-memory profile is experimental and may fail to start or run slowly.

Do not use this free setup for a world you cannot afford to lose. Make backups whenever possible.

## Private access

The whitelist is enabled and intentionally has no player names yet. Add the owner's and invited player's exact in-game usernames before allowing connections. Keep LoginSecurity enabled because Eaglercraft servers use offline-mode authentication.

Never commit passwords, access tokens, or other secrets to this repository.

## Deploy

1. Sign in to Render.
2. Create a new **Blueprint** and connect this GitHub repository.
3. Select `render.yaml` as the Blueprint file.
4. Review the service settings and deploy.
5. After deployment, use the Render service's HTTPS hostname as a secure WebSocket address (`wss://...`) in a compatible Eaglercraft client.

The deployment is not complete until the whitelist usernames are configured and the server passes a connection test.

## Credits

The container is based on the public `itzg/minecraft-server` Docker image. Eaglercraft browser connectivity is provided by EaglerXServer. LoginSecurity provides in-game account registration and login.
