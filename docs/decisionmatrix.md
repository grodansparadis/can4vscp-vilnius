# Decision Matrix

The full functionality of the decision matrix is explained [in the
specification](http://www.vscp.org/docs/vscpspec/doku.php?id=decision_matrix).

Vilnius have a decision matrix consisting of eight entries. This matrix can be used to control the I/O channels. Possible actions are listed in the table below.

|  Action | Action code | Parameter | Description |
|---------|-------------|-----------|-------------|
|  **NOOP**        | 0           | Not used  | No operation. Will do absolutely nothing. |
|  **SET**         | 1           | Channel (0-1) | Set output of I/O channel high. | The argument is an integer where 0 is output 0 and so on and can be in the range 0-1. |
|  **CLR**         | 2           | Channel (0-1) | Set output of I/O channel low. | The argument is an integer where 0 is output 0 and so on and can be in the range 0-1. |
|  **TOGGLE**      | 3           | Channel (0-1) | Toggle output for output I/O channel given by argument. The argument is an integer where 0 is output 0 and so on and can be in the range 0-1. Does not have any meaning for a channel set as input. |
|  **STATUS**      | 4           | *sensorindex* | Works the same as when the module receive a [CLASS1.CONTROL,SYNC](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.control?id=type26) event with the exception that zone/sub zone always is the same as of the module. |
|  **STATUSALL**   | 5           | Not used | same as **STATUS** above but without the *sensorindex* argument. Will report info for all channels and types. |


## Example

You want to activate output I/O 0 when a [CLASS1.CONTROL, TurnOn, Type=5
event](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.control?id=type5)
is received.

A matrix row consist of

|  Byte |  Description |
  ------ | -------------
  0      |  oaddr
  1      |  flags
  2      |  class-mask
  3      |  class-filter
  4      |  type-mask
  5      |  type-filter
  6      |  Action code
  7      |  Action parameter

So for example if you populate the row with the following values

 |  Byte |  Value      | Description
  ------ |  ---------- | ------------------
  0      |  **0x00**  | oaddr
  1      |  **0x80**  | flags
  2      |  **0xff**  | class-mask
  3      |  **0x1e**  | class-filter
  4      |  **0xff**  | type-mask
  5      |  **0x05**  | type-filter
  6      |  **0x01**  | Action code
  7      |  **0x01**  | Action parameter

-   **oaddr** set to zero as i is not used.
-    **flags** have one bit set. Enable row. We could have set bit 4
    Match Zone to test zone also trigger DM.
-   **class-mask** is set to 0xff as we have just one event we will trigger on.
-   **class-filter** is set to CLASS1.CONTROL.
-   **type-mask** is set to 0xff as we have just one event we will trigger on.
-   **type-filter** is set to 5 which is TurnOn.
-   **Action code** i set to the SET action.
-   **Action parameter** 1 is I/O 0 so this channel will be set high if configured as an output.



[filename](./bottom-copyright.md ':include')
