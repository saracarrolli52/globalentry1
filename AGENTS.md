<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->
- Products and orders live in Lovable Cloud; all reads/writes go through server functions in src/lib/store.functions.ts. Why: order prices are computed server-side and admin access is enforced there.
- /admin is protected by a shared passcode (ADMIN_PASSCODE) stored in an encrypted session cookie (SESSION_SECRET); every admin server function re-checks the session. Why: no user accounts needed for a single-owner shop.
