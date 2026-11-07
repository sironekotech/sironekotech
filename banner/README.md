# バナーの作り直し

`profile/banner-light.png` と `profile/banner-dark.png` は、このフォルダの `banner.html` を Chrome で書き出した画像です。文言や色を変えたら、このフォルダで次を実行して作り直します。

```bash
C="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
for m in light dark; do
  h=""; [ "$m" = dark ] && h="#dark"
  "$C" --headless=new --disable-gpu --hide-scrollbars --force-device-scale-factor=2 \
    --default-background-color=00000000 --window-size=900,220 --virtual-time-budget=8000 \
    --screenshot="../profile/banner-$m.png" "file://$PWD/banner.html$h"
done
```

色は sironekotech-design のトークンの値だけを使います。猫の絵（`cat.png`）は sironekotech-hp の `public/cat-assets/main.png` と同じものです。
