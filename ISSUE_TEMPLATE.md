### Issue

### Bluetooth Logs
If your issue is related to bluetooth communication, please include logs gathered with `RZBSetLogHandler`. Be aware that the log may contain sensitive information, and you may want to obfuscate the log. If you ignore the log levels `RZBLogLevelWriteCommandData` and `RZBLogLevelDelegateValue`, none of the transmitted NSData is included in the log. IE:

```obj-c
RZBSetLogHandler(^(RZBLogLevel logLevel, NSString *format, va_list args) {
    if (logLevel != RZBLogLevelWriteCommandData && logLevel != RZBLogLevelDelegateValue) {
        NSLog(@"%@",  [[NSString alloc] initWithFormat:format arguments:args]);
    }
});
```
