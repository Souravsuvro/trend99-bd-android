# Trend99 BD Android

Native Java Android preview, reconstructed from the earlier source with an injectable transport for emulator UI tests. Public source, no private credentials or customer data. Supabase publishable client key only.

## CI
GitHub Actions uses a standard Ubuntu runner to build a debug APK and run four controlled-response Espresso journey tests: valid login, invalid login, district/total/COD confirmation, and server stock rejection with stable retry key. Test transport intercepts all requests: these are NOT live Supabase integration tests and do not mutate production data. No artifact upload or Gradle cache storage is enabled. APK is built on the runner but not downloadable unless an artifact/release step is separately approved.

## Build
JDK 17, Gradle 8.9, Android SDK 35. Run `gradle assembleDebug` and `gradle connectedDebugAndroidTest` with an emulator. No Gradle wrapper included yet.

## Limitations
Preview supports one product per cart, in-memory token/cart, no token refresh, no AI ranking, no owner controls or images, no full Bangla localization. Earlier source supported multiple products; this reconstructed testable version narrows cart scope explicitly. Not production-ready. Live credentials and disposable catalog/order fixtures must be provisioned securely before separate live tests. Do not put test passwords or service-role keys in source.
