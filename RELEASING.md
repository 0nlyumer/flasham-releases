# Nayi release kaise publish karein (runbook)

1. `sale_orders_app/android/app/build.gradle` mein `versionCode` +1 aur `versionName`
   usi number par rakho (masalan versionCode 10 / versionName "1.10").
   Usool: versionCode hamesha versionName ke number ke barabar (1.9 -> 9, 1.10 -> 10).
2. Laptop route se APK banao (build-flasham3.bat) — file ka naam `FlashAM-v<versionName>.apk`.
3. Is repo mein naya GitHub Release banao, tag `v<versionName>`, APK asset attach karo
   (asset ka naam bilkul `FlashAM-v<versionName>.apk` ho):
   `gh release create v1.10 FlashAM-v1.10.apk --repo 0nlyumer/flasham-releases --title "FlashAM 1.10" --notes "..."`
4. `version.json` update karke push karo: versionCode, versionName, apkUrl
   (`https://github.com/0nlyumer/flasham-releases/releases/download/v<versionName>/FlashAM-v<versionName>.apk`),
   notes (chhoti, user ke liye), publishedAt.
5. Bas — tamam purani installs ko app khulte hi update popup mil jayega.
   App version.json yahan se parhti hai:
   https://raw.githubusercontent.com/0nlyumer/flasham-releases/main/version.json
