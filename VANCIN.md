# Servidor de suporte Vancin (rustdesk-server 1.1.16 + patch)

Patch em `src/rendezvous_server.rs`:
- registro de dispositivo (`RegisterPk`) pela conexão TCP/WebSocket — o original responde `NOT_SUPPORT`;
- a conexão registrada recebe `PunchHole`/`RequestRelay` e heartbeat vazio a cada 15 s (keep_alive 30 s);
- atrás de proxy (X-Real-IP), mantém a porta da conexão para cada cliente ter endereço único.

Com isso o cliente funciona inteiro pela 443 (wss://dominio/ws/id e /ws/relay via NPM).
Licença: AGPL-3.0 (mesma do projeto original).
