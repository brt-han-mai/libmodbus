# modbus_rtu_set_hw_echo_params

## Name

modbus_rtu_set_hw_echo_params - configure hardware echo parameter

## Synopsis

```c
int modbus_rtu_set_hw_echo_params(modbus_t *ctx, int is_echo, int us);
```

## Description

The *modbus_rtu_set_hw_echo_params()* function shall configure hardware echo
mode for the input context `ctx`. The hardware echo mode, if enabled, will
ignore echoed bytes received after a modbus frame has been sent. To enable
hardware echo mode, set the `is_echo` parameter to `TRUE`. To disable it, set
the `is_echo` parameter to `FALSE`. The `us` parameter specifies the timeout (in
microseconds) for an echoed-byte reading.

This function can only be used with a context using a RTU backend.

## Return value

The function shall return 0 if successful. Otherwise it shall return -1 and set
errno to one of the values defined below.

## Errors

- *EINVAL*, the libmodbus backend is invalid or not RTU or the `us` is negative.
