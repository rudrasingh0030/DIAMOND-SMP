# DIAMOND-SMP

A small private Eaglercraft survival server project.

## Planned server

- Minecraft/Paper: 1.12.2
- Client: compatible Eaglercraft 1.12.2
- Game mode: Survival
- Difficulty: Normal
- Keep inventory: off (Minecraft default)
- Player access: whitelist enabled for the configured usernames
- Authentication: LoginSecurity plugin

## Hosting notes

This repository includes a Render Blueprint for a free test deployment. It is not a guarantee of an always-online server.

Important limitations:
- Free web services can spin down after 15 minutes without inbound traffic and may take about a minute to wake up.
- Render can restart a free service at any time.
- Free web services do not support persistent disks. World data, player progress, and plugin data can be lost after a restart, suspension, or redeploy.
- The low-memory profile is experimental and may fail to start or run slowly.

Do not use this free setup for a world you cannot afford to lose.

## Private access

The whitelist is enabled for the usernames configured in `render.yaml`. Check the exact in-game spellings before deploying. LoginSecurity is included because the server uses offline-mode authentication. Each player should register a unique password in-game and must not reuse a personal account password.

## Deploy

Use Render's **Blueprint** flow so Render reads the `render.yaml` file in this repository:

1. In Render, choose **New → Blueprint** (not Web Service).
2. Connect `rudrasingh0030/DIAMOND-SMP`.
3. Select `render.yaml` if asked for a Blueprint file.
4. Review the service plan. It must say **Free / $0**, not $7/month or another paid amount.
5. Deploy only after confirming the plan is Free.

The deployment is not complete until the build succeeds and the server passes a connection test. After deployment, use the Render HTTPS hostname as a secure WebSocket address (`wss://...`) in a compatible Eaglercraft client.

## Credits

The container is based on the public `itzg/minecraft-server` Docker image. Eaglercraft browser connectivity is provided by EaglerXServer. LoginSecurity provides in-game account registration and login.
