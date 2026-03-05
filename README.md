# QRLWallclock

A QRL Wallclock Go package

## Installation

```bash
go get github.com/theQRL/qrlwallclock
```

## Usage

```go
package main

import (
  "fmt"
  "time"

  "github.com/theQRL/qrlwallclock"
)
 
func main() {
  genesisTime, _ := time.Parse(time.RFC3339, "2020-01-01T12:00:23Z")

  wallclock := qrlwallclock.NewQRLBeaconChain(genesisTime, 12*time.Second, 32)

  slot, epoch, err := wallclock.Now()
  if err != nil {
    panic(err)
  }

  fmt.Println("Slot: ", slot)
  fmt.Println("Epoch: ", epoch)
}
```
