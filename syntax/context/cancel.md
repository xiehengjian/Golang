```go
ctx,cancel:=context.WithCancel(context.Background())

go func(){
	for {
		select {
			// when someone call cancel(),this goroutine will return
			case <-ctx.Done():
				return 
			default:
				// do something else
		}
	}
}
```