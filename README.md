# Grid & Perspective

A drawing helper. Load any photo, lay a grid over it, and find the photo's perspective —
then print the matching grid for your paper.

Everything runs in the browser. **The photo is never uploaded anywhere** — it is read straight
off your device, and nothing is sent over the network. Settings are remembered on the browser;
the photo is not.

## Using it

Open `index.html` in a browser. Load a photo (choose, drag & drop, or paste).

**Crop** — trim the photo to the bit you want to draw, free-form or locked to a shape (square, 4:3,
3:4, 3:2, 2:3) so it matches your paper. Non-destructive: the original is kept and one button puts it
back.

**Grid** — the classic transfer method. Pick 3×3, 4×4, 5×5 (or set columns and rows yourself),
label the squares A1/B2, and copy one square at a time. Tick *Square cells* so a square on the
photo is the same shape as a square on your paper.

**Perspective** — set the horizon (your eye level), then drag the vanishing points until the
guide lines lie along the real edges in the photo:

| Mode | When |
|---|---|
| 1-point | facing something square-on — a corridor, a road going away |
| 2-point | looking at a corner — a building from the street |
| 3-point | looking up at a tower, or down from height — uprights lean to a third point |

Vanishing points usually sit off the sides of the picture; the app zooms out automatically so
you can still reach their handles.

**Plane grid** — a flat grid can't show depth. Drag four corners onto a flat surface *inside*
the photo (floor, table top, wall) and the app splits it into true perspective squares that
shrink as they go back. It also extends that surface's own edges until they meet, which shows
you where the vanishing points and the real horizon actually are.

**Colour** — a painter's wheel (red / yellow / blue), so the opposites are the ones that matter when
you paint: red&harr;green, blue&harr;orange, yellow&harr;violet. Round the wheel is the colour, inwards is
its strength — pure, strong, medium, weak. Mixing is done in RYB, so blue + yellow really makes green
and a colour mixed with its opposite really goes muddy. Two ways to weaken a colour are shown side by
side: water/white (paler) versus a touch of the opposite colour (quieter, not paler). You can also tap
the photo to lift a colour off it and be told what to mix to match it.

**Save** — download or print the photo with everything drawn on it, and download or print the
matching blank grid for your paper (A4 upright, A4 sideways, or the photo's own shape).

## Hosting it (optional)

Handy if you want it on a phone or tablet next to the drawing board. It is a single static
file, so any static host works. To run it in Docker behind Traefik, like the other apps:

```
docker compose up -d --build
```

Set the host rule in `docker-compose.yml` to whatever domain you point at it.

## Files

- `index.html` — the whole app (no build step, no dependencies)
- Hosted with GitHub Pages at https://labubuglue.github.io/grid-perspective/ once Pages is switched on
- `Dockerfile` / `docker-compose.yml` — optional nginx container
