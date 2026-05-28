# LBF Studio — Email Signature

Two signature files are included. Use the one that matches your email client.

---

## Which file to use?

| File | Best for | Images |
|---|---|---|
| `signature.html` | Gmail · Apple Mail · Outlook Mac · Outlook Web · Yahoo | Inline SVG — no hosting needed |
| `signature-outlook.html` | Outlook for Windows (2016 / 2019 / 365) | PNG — requires image hosting |

---

## File overview

```
Email-Signatures/
├── signature.html          ← Primary (inline SVG, no image hosting required)
├── signature-outlook.html  ← Outlook for Windows (PNG, needs hosted images)
├── elements/
│   ├── Logo.svg            ← Logo source (vector)
│   ├── Logo@2x.png         ← Logo PNG (for Outlook version)
│   ├── IG Icon.svg         ← Instagram icon source
│   └── IG Icon@2x.png      ← Instagram icon PNG (for Outlook version)
└── README.md               ← You are here
```

---

## Links configured

| Element | Destination |
|---|---|
| Logo | https://lbf.studio/ |
| Instagram icon | https://www.instagram.com/letsbefriends.tv |
| Watch Showreel | https://youtu.be/qkz4Nc359y0?si=-WkiAp7lSjDGaGZk |

---

## Setup for `signature-outlook.html` (image hosting)

Before using the Outlook version, upload the PNG images to a public web server and update the `src` URLs in the file.

**Step 1 — Upload images**

Upload both files to a publicly accessible server:
- `elements/Logo@2x.png`
- `elements/IG Icon@2x.png`

Suggested location: `https://lbf.studio/assets/email/`

**Step 2 — Update the HTML**

Open `signature-outlook.html` and replace the two placeholder image URLs (marked with 🔗 in the comments):

```
https://lbf.studio/assets/email/lbf-logo.png    ← replace with your hosted URL
https://lbf.studio/assets/email/lbf-ig-icon.png ← replace with your hosted URL
```

---

## Installation by email client

---

### Gmail (web)

1. Open `signature.html` in **Chrome or Firefox**
2. Press **⌘A** to Select All, then **⌘C** to Copy
3. In Gmail, go to **Settings** (⚙) → **See all settings** → **Signature** tab
4. Click **Create new**, give it a name (e.g. "LBF Studio")
5. Click inside the signature text box and press **⌘V** to Paste
6. Scroll down and click **Save Changes**

> **Tip:** If images don't appear after pasting, try pasting in a private window, or use the image icon in the toolbar to re-insert images from your computer.

---

### Apple Mail

**Option A — Paste method (quickest)**

1. Open `signature.html` in **Safari**
2. Press **⌘A** then **⌘C**
3. In Mail, go to **Mail → Settings → Signatures**
4. Click **+** to create a new signature
5. Delete the placeholder text, then press **⌘V** to paste
6. Drag the signature to your email account in the left column

**Option B — File replacement method (most reliable)**

1. In Mail, create a new signature with any placeholder text (e.g. "LBF")
2. Quit Mail completely
3. In Finder, press **⌘⇧G** and go to:
   ```
   ~/Library/Mail/V10/MailData/Signatures/
   ```
   *(The `V10` folder number may differ — try V9, V11 if V10 doesn't exist)*
4. Sort by Date Modified — the newest `.mailsignature` file is your placeholder
5. Open it with a text editor (right-click → Open With → TextEdit)
6. Replace everything **below** the `<body>` tag with the contents of `signature.html`'s `<body>` section
7. Save the file, then right-click it → **Get Info** → tick **Locked** (prevents Mail from reverting it)
8. Reopen Mail — the signature should appear

---

### Outlook for Mac

1. Open `signature.html` in **Safari**
2. Press **⌘A** then **⌘C**
3. In Outlook, go to **Outlook → Settings → Signatures**
4. Click **+** to create a new signature
5. Click into the editor area and press **⌘V** to paste
6. Give it a name and click **Save**
7. Set it as your default signature for new messages / replies

---

### Outlook for Windows

Use **`signature-outlook.html`** (not `signature.html`) for this client.

> ⚠️ You must complete the [image hosting setup](#setup-for-signature-outlookhtml-image-hosting) first.

**Method A — Signature editor (recommended)**

1. In Outlook, go to **File → Options → Mail → Signatures**
2. Click **New**, give it a name
3. In the editor, paste — but first open `signature-outlook.html` in **Edge or Chrome**, Select All, Copy, then paste into the Outlook signature box
4. Click **OK**

**Method B — Direct HTML file**

1. Find the Outlook signatures folder:
   - Windows 11/10: `%APPDATA%\Microsoft\Signatures\`
   - In Run (⊞ + R), type: `%APPDATA%\Microsoft\Signatures`
2. Create a new folder named `LBF Studio_files`
3. Copy `elements/Logo@2x.png` and `elements/IG Icon@2x.png` into it
4. Save `signature-outlook.html` as `LBF Studio.htm` in the Signatures folder
5. Restart Outlook and select "LBF Studio" as your signature

> **Note:** Outlook for Windows blocks remote images by default. Using hosted images (Method B) or embedding images as CID attachments gives the most reliable results.

---

### Yahoo Mail

1. Open `signature.html` in **Chrome or Firefox**
2. Press **⌘A** then **⌘C**
3. In Yahoo Mail, go to **Settings** (⚙) → **More Settings** → **Writing email**
4. Enable **Signature**, click into the text box
5. Press **⌘V** to paste
6. Click **Save**

---

### Thunderbird

1. In Thunderbird, go to **Tools → Account Settings**
2. Select the account, scroll to **Signature text**
3. Tick **Use HTML**
4. Open `signature.html` in a text editor, copy the entire content
5. Paste into the signature box
6. Click **OK**

---

## Customisation

### Changing personal details

If you need to add a name, title, or phone number above the logo row, insert an additional `<tr>` block **before** the first row in the table:

```html
<!-- Add above the Logo row -->
<tr>
  <td colspan="2" style="padding:20px 20px 0 25px;font-family:Arial,Helvetica,sans-serif;font-size:12px;line-height:16px;color:#313131;">
    <strong style="font-weight:bold;">Your Name</strong><br>
    <span style="color:#797A83;">Job Title</span>
  </td>
</tr>
```

### Changing colours

The brand colours used in this signature:

| Token | Hex | Usage |
|---|---|---|
| Primary/Charcoal | `#313131` | Logo, links, icons |
| Primary/Smoke | `#797A83` | Disclaimer text |

### Adding or removing links

All three links are clearly marked with `href="..."` attributes in the HTML. Find and replace as needed.

---

## Troubleshooting

**Images not showing in Gmail**
Gmail sometimes strips images when pasting HTML. Try: in Chrome, open the HTML file → right-click the page → Inspect → copy the outer HTML, then paste that into Gmail's signature editor.

**Signature looks different in Outlook (Windows)**
Use `signature-outlook.html` instead of `signature.html`. Outlook's rendering engine doesn't support inline SVGs.

**Logo appears too large or too small**
The logo is set to 127×16px display size using explicit `width` and `height` attributes. If your email client is overriding this, add `!important` to the inline width/height styles.

**Disclaimer text is too small to read**
Some email clients enforce a minimum font size. The disclaimer is set to 7px as per the design. If readability is a concern, change `font-size:7px` to `font-size:9px`.

**Links not working**
Make sure the `href` values include `https://` — bare domain links may not be recognised by all clients.

---

*Signature designed by LBF Studio · [lbf.studio](https://lbf.studio/)*
