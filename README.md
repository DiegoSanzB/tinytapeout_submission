![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg)

# UCHILE-FCFM 7 Segment Display

This is a project done at the Faculty of Physical Sciences and Mathematics (fcfm in spanish) in the University of Chile by students of the Electrical Civil Engineering department. The design consists of a ripple counter made from DSR flip-flops which acts as a clock to show the characters of 'UCHILE-FCFM-', the relation between the counter bits and the 7-segment leds was optimized with the Quine McCluskey algorithm. The output uses the standard 7-segment display leds segments, input info is in the :

| # | Input           | Description                                                                  |
|---|-----------------|------------------------------------------------------------------------------|
| 0 | clock           | clock for the counter                                                        |
| 1 | reset           | reset counter                                                                |
| 2 | none            | -                                                                            |
| 3 | counter_disable | disables the counter output and uses the 4th-7th input as the counter value. |
| 4 | A               | most significant bit of the counter                                          |
| 5 | B               |                                                                              |
| 6 | C               |                                                                              |
| 7 | D               | least significant bit of the counter                                         |

Truth table used for the design, ABCD are the counter bits and a, b, c, d, e, f, g are the 7-segment display leds:

| Counter | Character | A | B | C | D | a | b | c | d | e | f | g |
|---------|-----------|---|---|---|---|---|---|---|---|---|---|---|
| 0       | U         | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 |
| 1       | C         | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 1 | 1 | 0 |
| 2       | H         | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 0 | 1 | 1 | 1 |
| 3       | I         | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1 | 1 | 0 |
| 4       | L         | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 | 0 |
| 5       | E         | 0 | 1 | 0 | 1 | 1 | 0 | 0 | 1 | 1 | 1 | 1 |
| 6       | -         | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |
| 7       | F         | 0 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 1 | 1 | 1 |
| 8       | C         | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 1 | 0 |
| 9       | F         | 1 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 1 | 1 | 1 |
| 10      | M         | 1 | 0 | 1 | 0 | 1 | 1 | 1 | 0 | 1 | 1 | 0 |
| 11      | -         | 1 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |

From the last table each segment boolean function was calculated using Quine McCluskey considering the miniterms 12 to 15 as don't cares.
