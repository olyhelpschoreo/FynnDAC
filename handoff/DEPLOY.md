# Vanity URL: fynnfamily.com/dadcouncil

The Dad Advisors Council page is hosted for you — you do **not** need to deploy
any files. All that's needed on fynnfamily.com is a redirect.

Live page:  https://olyhelpschoreo.github.io/FynnDAC/
Vanity URL: https://fynnfamily.com/dadcouncil

## The change (Firebase Hosting)

Add this to the `hosting` block of `firebase.json`, then `firebase deploy --only hosting`:

    "redirects": [
      {
        "source": "/dadcouncil{,/**}",
        "destination": "https://olyhelpschoreo.github.io/FynnDAC/",
        "type": 302
      }
    ]

If a `redirects` array already exists, just add the object to it.

The `{,/**}` glob makes both `/dadcouncil` and `/dadcouncil/` work, plus anything
typed after it.

## Please use 302, not 301

302 = temporary. 301 = permanent, and browsers cache it more or less forever —
if the page ever moves, anyone who visited once keeps getting sent to the old
place, and it is genuinely painful to undo. 302 costs nothing here and keeps
the door open.

## Note

Visitors will see the address bar change to the olyhelpschoreo.github.io URL
after the bounce. That was confirmed as acceptable. If that ever changes, the
fix is a CNAME record pointing a subdomain (e.g. dadcouncil.fynnfamily.com) at
olyhelpschoreo.github.io — one DNS record, and the page can then be served
under the Fynn name with no bounce at all.
