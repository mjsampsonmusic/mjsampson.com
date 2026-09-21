# mjsampson.com

Artist site for MJ Sampson. One page, no framework, no build step, no dependencies. Deployed on Cloudflare Pages.

**Live:** [mjsampson.com](https://mjsampson.com)

## Stack

Hand written HTML and CSS. The only network request beyond the page itself is the Google Fonts stylesheet. There is one line of JavaScript, which sets the year in the footer.

| File | Purpose |
| --- | --- |
| `index.html` | The whole page. Semantic sections for the single, the catalogue, the bio, the links and booking. |
| `styles.css` | Custom properties for the palette and type scale, then a mobile first layout using flexbox and grid. |
| `cover.jpg` | Cover artwork for the current single. |

## Notes on the build

- Mobile first. Every layout rule is written for a phone and widened with one `min-width` query, since most of the traffic arrives from an Instagram bio link.
- Type and spacing scale with `clamp()` rather than breakpoints, so there are no jumps between sizes.
- The ripple behind the wordmark is five absolutely positioned circles on a staggered CSS keyframe with a radial mask. It is disabled under `prefers-reduced-motion`.
- Safe area insets are applied at the root so the page clears the notch and the home indicator on iOS.
- Focus states are visible on every interactive element, images carry alt text, and contrast on the body text clears WCAG AA against the background.
- The artwork is procedurally generated rather than photographed. The ripple is a damped radial wave field shaded with a Blinn-Phong highlight model, rendered with NumPy.

## Running it locally

Clone the repo and open `index.html` in a browser. There is nothing to install.

To serve it over HTTP instead:

```bash
python3 -m http.server 8000
```

## Deploying

The repo is connected to a Cloudflare Pages project. Pushing to `main` publishes the site. There is no build command and the output directory is the repo root.

## License

The code in this repository is MIT licensed, see `LICENSE`. The music, lyrics, artist name and cover artwork are not covered by that license and remain the property of Mitchell Sampson.
