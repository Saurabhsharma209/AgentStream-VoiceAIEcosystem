# Rapida AI + Exotel — connector reference

Companion to [`docs/support/exotel-rapida-ai-sip-trunk.md`](../../../docs/support/exotel-rapida-ai-sip-trunk.md).

---

## Integration modes

| Mode | Rapida doc | Exotel side |
|------|------------|-------------|
| **Native Exotel** | [integrations/telephony/exotel](https://doc.rapida.ai/integrations/telephony/exotel) | App / Flow → `https://websocket-01.in.rapida.ai/v1/talk/exotel/call/...` |
| **SIP trunk** | [integrations/telephony/sip](https://doc.rapida.ai/integrations/telephony/sip) | vSIP trunk + **`destination-uris`** → `sip-01.in.rapida.ai:5060` + Connect **`sip:<trunk_sid>`** |

---

## Path A — webhook (summary)

- **Rapida:** External integrations → **Exotel** credential (**Account SID**, **Client ID**, **Client Secret** per Rapida UI).  
- **Rapida:** Phone deployment → provider **Exotel**, **App ID**, **phone number**.  
- **Exotel:** Flow / applet URL + DID assignment — follow [Rapida Exotel](https://doc.rapida.ai/integrations/telephony/exotel).

---

## Path B — SIP (summary)

- **Rapida ingress:** `sip:sip-01.in.rapida.ai:5060` (UDP/TCP, PCMU/PCMA).  
- **Exotel:** [`docs/support/_exotel-trunk-api-snippets.md`](../../../docs/support/_exotel-trunk-api-snippets.md) for trunk, DID, credentials, destination-uris.  
- **Rapida:** SIP Trunk credential with **SIP URI** = Exotel **edge IP:port** when Rapida must register/invite **toward** Exotel for PSTN.

---

## Outbound API (Rapida)

`POST https://api.rapida.ai/v1/talk/call` with `Authorization: Bearer` — see [Rapida Exotel](https://doc.rapida.ai/integrations/telephony/exotel) for JSON shape.

---

## References

- [Rapida — Exotel](https://doc.rapida.ai/integrations/telephony/exotel)  
- [Rapida — SIP](https://doc.rapida.ai/integrations/telephony/sip)  
- [Exotel SIP API](https://docs.exotel.com/dynamic-sip-trunking/detailed-sip-trunking-api-reference)
