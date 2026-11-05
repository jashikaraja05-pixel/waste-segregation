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

## Architecture decisions

- ECO-LENSAI migrated in from a code archive (5 Nov 2026). The scans schema was ported from the source's Drizzle migration into Lovable Cloud migrations (`supabase/migrations/`); Drizzle is no longer used.
- `backend/` holds the optional Python FastAPI classifier. It is not trained, not deployed, and not connected — classification runs through the `classifyWaste` server function via the Lovable AI Gateway unless `PYTHON_CLASSIFIER_URL` is set as a secret.
