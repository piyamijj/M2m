# Sesli Tercüman — M2M

Türkçe ⇄ Farsça, **tamamen çevrimdışı** sesli tercüman (Android).

Bu depo, **M2M-100 418M (int8)** çeviri motorunu kullanan sürümdür.
Kardeş depo: [Nllb](https://github.com/piyamijj/Nllb)

## İndir

Son APK: [Releases → latest](https://github.com/piyamijj/M2m/releases/latest)

Doğrudan bağlantı:

```
https://github.com/piyamijj/M2m/releases/download/latest/SesliTercuman-M2M-v0.1.0.apk
```

## Durum

| Bileşen | Durum |
|---|---|
| Arayüz (Compose) | ✅ |
| Mikrofon izni | ✅ |
| Konuşma tanıma (Whisper base) | ⏳ Faz 1 |
| Çeviri (M2M) | ⏳ Faz 2 |
| Seslendirme (Piper) | ⏳ Faz 3 |

## Mimari (hedef)

```
Mikrofon → VAD → Whisper base (int8) → M2M (int8, ONNX) → Piper TTS
```

Hepsi cihazda çalışır; uygulama internete ihtiyaç duymaz.

## Derleme

APK, GitHub Actions ile otomatik üretilir (`.github/workflows/android.yml`).
Her `main` push'unda yeni APK `latest` sürümüne eklenir.

Yerelde:

```bash
./gradlew :app:assembleRelease
```

Gereksinimler: JDK 17, Android SDK 35.

## Lisans

Uygulama kodu MIT. M2M-100 model ağırlıkları **MIT**.
