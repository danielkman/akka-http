# pathEndOrSingleSlash

## Signature

@@signature [PathDirectives.scala]($akka-http$/akka-http/src/main/scala/akka/http/scaladsl/server/directives/PathDirectives.scala) { #pathEndOrSingleSlash }

## Description

Only passes the request to its inner route if the unmatched path of the `RequestContext` is either empty
or contains only one single slash.

This directive is a simple alias for `rawPathPrefix(Slash.? ~ PathEnd)` and is mostly used on an inner-level to
discriminate "path already fully matched" from other alternatives (see the example below). For a comparison between path directives check @ref[Overview of path directives](index.md#overview-path-scala).

It is equivalent to `pathEnd | pathSingleSlash` but slightly more efficient.

## Example

@@snip [PathDirectivesExamplesSpec.scala]($test$/scala/docs/http/scaladsl/server/directives/PathDirectivesExamplesSpec.scala) { #pathEndOrSingleSlash- }