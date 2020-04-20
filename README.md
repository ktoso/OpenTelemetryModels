# OpenTelemetryModels

Swift Package wrapper around the OpenTelemetry models defined as protobufs

Uses the OpenTelemetry proto's from a submodule:

    brew install swift-protobuf
    git submodule update --init
    ./scripts/generate_sources.sh
    swift test

The models have some basic conveniences added alongside the raw protobuf
models, as well as aliasing to slightly nicer names, to try and make this
easier to use.

This is **NOT** a full tracer library implementation, and doesn't do anthing
about storing, transfering, or sampling for the underlying models. The
convenience methods in this library are about creating, inspecting, and
manipulating trace spans directly.

## Using OpenTelemetryModels

```swift doctest
import OpenTelemetryModels

let bareSpan = OpenTelemetry.Span.start(name: "foo") // => Int = 2
```
