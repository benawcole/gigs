# Embedding on benawcole.com/schedule

In the Adobe Portfolio editor, open the Schedule page, add an **Embed** block where the
gigs list should go, paste this, and click Publish:

```html
<iframe id="benawcole-gigs" src="https://benawcole.github.io/gigs/" title="Upcoming gigs"
        style="width:100%;height:600px;border:0;background:transparent" scrolling="no"
        allowtransparency="true"></iframe>
<script>
  addEventListener("message", function (e) {
    if (e.origin === "https://benawcole.github.io" && e.data && e.data.benawcoleGigsHeight) {
      document.getElementById("benawcole-gigs").style.height = e.data.benawcoleGigsHeight + "px";
    }
  });
</script>
```

The script resizes the frame to fit the list. If Portfolio removes the `<script>`
part, the frame stays at 600px; change `height:600px` to suit.
