# Change Log

Notable changes to threescalers will be tracked in this document.

## 0.7.0 - 2020-10-28

### Compatibility

- [__BREAKING__] This release is a breaking change from previous releases due to
  public functions and types changing signatures.

### Added

- Added no_std mode. Disable default features to get it unless you enable the "std"
  feature. We now use anyhow to generate errors in fallible functions. ([#69](https://github.com/3scale-rs/threescalers/pull/69))

### Changed

- The timestamps used are now simple integers removing the complexity of using
  SystemTime implementations. ([#73](https://github.com/3scale-rs/threescalers/pull/73))
- Updated the XML parsing crate serde-xml-rs to 0.4 ([#72](https://github.com/3scale-rs/threescalers/pull/72))

### Removed

- Removed the mandatory dependencies on error_chain and the http crate. ([#71](https://github.com/3scale-rs/threescalers/pull/71))

## 0.6.1 - 2020-10-08

### Compatibility

- This release is again usable with newer (and hopefully older) nightlies and makes
  use of new facilities on 1.47.0. ([#70](https://github.com/3scale-rs/threescalers/pull/70))

## 0.6.0 - 2020-05-03

### Changed

- [__BREAKING__] Introduce typed extensions. ([#67](https://github.com/3scale-rs/threescalers/pull/67))

### Compatibility

- This release is a breaking change from the 0.5 series if you use extensions.

## 0.5.0 - 2020-02-11

### Changed

- [__BREAKING__] Support for http 0.1 and reqwest 0.9 series has been dropped in favor
  of the http 0.2 and reqwest 0.10 series. ([#66](https://github.com/3scale-rs/threescalers/pull/66))
- Depend internally on percent_encoding 0.2. ([#65](https://github.com/3scale-rs/threescalers/pull/65))

### Compatibility

- This release is a breaking change from the 0.4 series.

## 0.4.0 - 2020-02-02

### Changed

- [__BREAKING__] The Usage type now tracks string slices rather than cloning them.
  Currently this means that users will need to pass in usage data already as string
  slices rather than integer types, though helpers or a Cow type might be added
  later on. This is internally represented as a vector that the caller can access.
  ([#63](https://github.com/3scale-rs/threescalers/pull/63))

### Fixed

- Replace uses of the method [T]::into_iter() with [T]::iter(). This was deprecated
  in Rust 1.41.0. ([#59](https://github.com/3scale-rs/threescalers/pull/59))

### Compatibility

- This release is a breaking change from the 0.3 series.

## 0.3.0 - 2019-09-24

### Added

- The dependencies for this project are checked by LicenseFinder to be free
  software licenses compatible with this project (ie. many/most of them, it's
  a non comprehensive list so far). ([#56](https://github.com/3scale-rs/threescalers/pull/56))

### Changed

- The date parsing for XML responses now returns an error to the caller rather
  than panicking/aborting. ([#55](https://github.com/3scale-rs/threescalers/pull/55))
- [__BREAKING__] The `Timestamp` type now supports `SystemTime` types from
  before the UNIX epoch on systems that support those. ([#55](https://github.com/3scale-rs/threescalers/pull/55))

### Compatibility

- This release is a breaking change from the 0.2 series.

## 0.2.0 - 2019-07-19

### Added

- The curl::Easy and curl::Easy2 APIs of curl are now supported. ([#43](https://github.com/3scale-rs/threescalers/pull/43), [#48](https://github.com/3scale-rs/threescalers/pull/48), [#50](https://github.com/3scale-rs/threescalers/pull/50))
- Parsing of AuthRep responses via serde. ([#27](https://github.com/3scale-rs/threescalers/pull/27), [#39](https://github.com/3scale-rs/threescalers/pull/39), [#42](https://github.com/3scale-rs/threescalers/pull/42), [#44](https://github.com/3scale-rs/threescalers/pull/44), [#49](https://github.com/3scale-rs/threescalers/pull/49))
- Added a report example for Reqwest. ([#37](https://github.com/3scale-rs/threescalers/pull/37))

### Changed

- The trait that supported clients implement has changed. ([#47](https://github.com/3scale-rs/threescalers/pull/47))
- [__BREAKING__] The Extensions type has had breaking changes. ([#36](https://github.com/3scale-rs/threescalers/pull/36), [#49](https://github.com/3scale-rs/threescalers/pull/49))
- The ToParams trait has been made private. ([#50](https://github.com/3scale-rs/threescalers/pull/50))

### Fixed

- The correct headers will be sent with the Reqwest client. ([#36](https://github.com/3scale-rs/threescalers/pull/36))
- Stop unnecessarily cloning the body in Reqwest. ([#40](https://github.com/3scale-rs/threescalers/pull/40))

### Compatibility

- This release is a breaking change from the 0.1 series.
