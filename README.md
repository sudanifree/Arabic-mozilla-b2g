# Arabic Mozilla B2G

> **Community project proposal:** investigate what it would take to port
> Mozilla Boot to Gecko (B2G) to Android 12, starting with an AOSP emulator.
> This is not a working Android 12 port or an installable build.

## Project status

B2G is a historical, archived project. The B2G source repository was archived
in 2021, its Gecko integration was removed from Mozilla's Gecko tree in 2017,
and the historical Gecko and Gonk sources available for this work date from
around 2016. The old B2G manifests target much older Android releases.

Consequently, changing an Android version number or syncing a newer Android
manifest is not enough to make B2G work. Gecko, Gonk, Android platform
interfaces, build tools, and device support all need investigation and likely
substantial porting. No Android 12 compatibility is currently claimed.

## Goal

Explore a maintainable, open-source path to run B2G as a complete operating
system on **one AOSP Android 12 emulator target first**. Supporting a physical
Android TV box or multiple processors is a later, separate goal: each device
needs its own kernel, boot chain, hardware configuration, and drivers.

## Why help is needed

- **Gecko:** Determine whether B2G's removed platform integration can be
  restored or reimplemented against a maintainable Gecko version.
- **Gonk:** Assess and port boot, graphics, input, audio, networking, storage,
  permissions, and other system services to the selected Android 12 target.
- **Android interfaces:** Identify obsolete APIs and libraries and map them to
  supported Android 12 interfaces.
- **Build and tooling:** Reproduce a complete build with supported host tools,
  dependencies, and an Android 12 source tree.
- **Testing and recovery:** Validate emulator boot and core functionality
  before attempting any physical device.

## Proposed milestones

1. Agree on the exact AOSP Android 12 emulator target and document a
   reproducible development environment.
2. Obtain and build the matching AOSP target without B2G to establish a
   working baseline.
3. Inventory Gecko/Gonk dependencies and create a porting plan with testable
   milestones.
4. Port and build one integration at a time; record blockers and test results.
5. Demonstrate a bootable emulator image before considering hardware-specific
   Android TV ports.

These are proposed milestones, not completed work. A complete AOSP checkout
and build need substantial disk space and compute resources; the manifest
alone is not the source tree.

## How to contribute

Contributions are welcome from people experienced in Gecko, Android platform
development, Gonk/B2G, graphics, embedded Linux, build systems, and testing.
Useful first contributions include:

- documenting reproducible source revisions and build prerequisites;
- auditing a specific Gecko-to-Android or Gonk-to-Android interface;
- proposing a small, independently testable porting task;
- testing on the agreed emulator target and sharing logs and exact steps.

Please include the device/target, source revision, host environment, commands
run, and complete relevant error output in reports. Discuss large architectural
changes before submitting them. Do not describe a manifest-only version bump
as Android 12 support.

## Safety

This project is experimental. Do not flash development images to a personal
phone or TV box. Physical-device work must be specific to the exact model, have
a documented recovery path, and be tested only by contributors who understand
the risk of an unbootable device.

## Historical references

- [Archived B2G build repository](https://github.com/mozilla-b2g/B2G)
- [B2G manifest repository](https://github.com/mozilla-b2g/b2g-manifest)
- [Gecko change removing the B2G top-level directory](https://github.com/mozilla/gecko-dev/commit/fc81db2822ef950297f091850941b9e40cd71a18)
- [AOSP Android 12 manifest](https://android.googlesource.com/platform/manifest/+/refs/tags/android-12.0.0_r1/default.xml)

## العربية

هذا مشروع مجتمعي استكشافي لدراسة ترحيل Mozilla B2G ليعمل كنظام كامل على
محاكي AOSP Android 12، ويبدأ بهدف واحد قابل للاختبار. **لا يوجد حاليًا منفذ
مكتمل أو صورة قابلة للتثبيت أو دعم مُثبت لـ Android 12.**

المصادر المتاحة تاريخية: أُرشف مستودع B2G عام 2021، وأُزيل تكامل B2G من شجرة
Gecko عام 2017، وتعود نسخ Gecko وGonk المرتبطة بالمشروع إلى نحو عام 2016.
لذلك يتطلب العمل ترحيلًا فعليًا لـ Gecko وGonk وواجهات Android وأدوات البناء،
وليس تغيير رقم إصدار في ملف manifest.

نرحب بمساهمات أصحاب الخبرة في Gecko وAndroid وGonk والبناء والاختبار. يرجى
تحديد الهدف وإصدارات المصادر وخطوات إعادة إنتاج المشكلة. لا تجرب تفليش صورة
على جهاز حقيقي؛ يجب أن يكون دعم كل جهاز محددًا بطرازه مع وجود خطة استعادة.
