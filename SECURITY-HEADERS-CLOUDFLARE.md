# Cloudflare Pages — Security Headers Setup

Cloudflare Pages uses the same `_headers` file format as Netlify.
The included `_headers` file works for both platforms.

## Additional Cloudflare-Specific Steps

1. Log in to your Cloudflare dashboard
2. Go to your domain → **SSL/TLS** → set to **Full (Strict)**
3. Go to **Edge Certificates** → enable **Always Use HTTPS**
4. Enable **HTTP Strict Transport Security (HSTS)**:
   - Max Age: 6 months (increase to 1 year after confirming HTTPS works)
   - Include subdomains: Yes (only if all subdomains use HTTPS)
   - Preload: Yes (submit to hstspreload.org after 1 year)

## HSTS Header (added by Cloudflare automatically when HSTS is enabled)
```
Strict-Transport-Security: max-age=15768000; includeSubDomains; preload
```

> Note: Do NOT add HSTS manually in _headers — let Cloudflare manage it
> to avoid locking yourself out if HTTPS ever breaks.
