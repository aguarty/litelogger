# litelogger
Very simple and lite logger with levels

## example:

```go
package main

import (
	logger "github.com/aguarty/litelogger"
)

type A struct {
	l *logger.Logger
}

func main() {
	a := A{}
	// log print to console and file with level "error"
	// path to file may be empty, so the logger don't write to file
	a.l = logger.Init("error", "./logs/asdasd.log")
	a.writelog("Hello, i'm a log message")
}

func (a *A) writelog(x string) {
	a.l.Debug("Debug - ", x)
	a.l.Info("info - ", x)
	a.l.Warn("warning - ", x)
	a.l.Errorf("Error - %v", x)
	a.l.Fatalf("Fatal - %v", x)
}
```