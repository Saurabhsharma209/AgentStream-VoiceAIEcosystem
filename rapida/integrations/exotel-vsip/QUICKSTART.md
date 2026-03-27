# Quickstart: Exotel + Rapida AI

**Rapida docs:** [Exotel](https://doc.rapida.ai/integrations/telephony/exotel) · [SIP trunk](https://doc.rapida.ai/integrations/telephony/sip)

---

## Path A — Native Exotel (no vSIP trunk API required)

1. **Rapida:** Integration → Tools → **Exotel** credential (Account SID + API-style fields per form).  
2. **Rapida:** Deploy → Phone → **Exotel**, **App ID**, Exotel **DID**.  
3. **Exotel:** Flow / applet → webhook:

   `https://websocket-01.in.rapida.ai/v1/talk/exotel/call/{assistant-id}?x-api-key={key}`

4. Assign Exotel number to the app.

---

## Path B — vSIP + Rapida SIP

1. **Exotel:** trunk → DID → optional digest → **`destination-uris`** → `sip-01.in.rapida.ai:5060` (transport per testing).  
2. **Exotel:** Connect **Dial whom** = **`sip:<trunk_sid>`**.  
3. **Rapida:** SIP Trunk credential → Exotel **edge IP:port** for outbound toward PSTN if needed.  
4. Snippets: [`docs/support/_exotel-trunk-api-snippets.md`](../../../docs/support/_exotel-trunk-api-snippets.md)

---

## Full article

[`exotel-rapida-ai-sip-trunk.md`](../../../docs/support/exotel-rapida-ai-sip-trunk.md)
