# KtorHttpBug

The bug is that for some reason, after updating from 1.4 to 1.5, requesting routes ending in / do not work the same way

## To reproduce

Open Terminal and execute the command:
`curl -v  0.0.0.0:8080/test`

And you should get: `HTTP/1.1 200 OK ... Success!`

But if you do: `curl -v  0.0.0.0:8080/test/` (note the slash)

You get `HTTP/1.1 404 Not Found`

This is unexpected. Especially because if you got to `gradle.properties` and change ktor_version to 1.4, both work!