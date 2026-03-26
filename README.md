# linkedclaims.com

Public website for the [LinkedClaims](https://identity.foundation/labs-linkedclaims/) project. Explains the spec, shows the ATProto lexicon schema, and embeds a live claims feed.

Static HTML/CSS/JS — no build step, deployed via GitHub Pages.

## Local Development

```bash
cd linkedclaims.com
python3 -m http.server 8080
# Open http://localhost:8080
```

The live claims feed fetches from the ATProto public API, so it works from any origin.

## Structure

```
index.html                          Main landing page
style.css                           Stylesheet
js/atproto-claims.js                <linked-claims-atproto> web component
lexicon/com-linkedclaims-claim.json Lexicon schema (displayed inline)
```

## Deployment (GitHub Pages)

1. Push this repo to GitHub
2. Go to Settings > Pages > Source: Deploy from branch `main`, folder `/ (root)`
3. Set custom domain to `linkedclaims.com`

## DNS Configuration

### GitHub Pages

Add these DNS records at your domain registrar:

```
linkedclaims.com.     A     185.199.108.153
linkedclaims.com.     A     185.199.109.153
linkedclaims.com.     A     185.199.110.153
linkedclaims.com.     A     185.199.111.153
www.linkedclaims.com. CNAME <your-github-username>.github.io.
```

### ATProto Domain Verification

To verify `linkedclaims.com` as the ATProto handle for the LinkedClaims account:

```
_atproto.linkedclaims.com. TXT "did=did:plc:xztctnvt5ycnsippd3orwqk7"
```

This allows the ATProto account `did:plc:xztctnvt5ycnsippd3orwqk7` to use `@linkedclaims.com` as its handle.

## Related

- [claim-atproto](https://github.com/nicholasgasior/claim-atproto) — TypeScript SDK for publishing LinkedClaims on ATProto
- [LinkedTrust](https://live.linkedtrust.us) — Web app for browsing and creating claims
- [DIF Labs LinkedClaims Spec](https://identity.foundation/labs-linkedclaims/) — The specification
