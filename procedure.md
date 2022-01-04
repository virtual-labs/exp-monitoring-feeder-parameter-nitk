<u>**Aim of the experiment: Monitoring Feeder parameter from workstation**</u>

<div style="text-align: justify">

Yokogawa CS 1000 (DCS) has Analog Input module which takes input from field for parameters such as voltage, current, power etc. The meters placed at appropriate locations in the substation will communicate the parameters to the workstation which will be displayed on Human-Machine Interface (HMI). These will be indication of Full load as well as circuit breaker tripping during over load conditions.

This process is simulated as below

1. Two feeders F1 and F2 are considered and data acquired from them is given to Analog Input Module of DCS.
2. To indicate increase in load current more bulbs in a particular feeder table is turned on by closing switches.
3. The current levels in feeders are

<div align="center">

| NUMBER OF SWITCHES CLOSED | CURRENT DETECTED(A) |
| ------------------------- | ------------------- |
| 1                         | 15                  |
| 2                         | 30                  |
| 3                         | 45                  |
| 4                         | 0                   |

</div>

4. 45A is Full Load of a feeder, and this message will be displayed in Pink color in workstation.
5. When 4th switch of a feeder is closed, crossing full load limit, then circuit breaker will be tripped. CB color changes to Blue. Feeder current becomes zero.
6. When a feeder circuit breaker trips, current in others settings changes accordingly.

The sample meter indications with loads on feeder are given below:

| NUMBER OF SWITCH CLOSED ON F1 | NUMBER OF SWITCH CLOSED ON F2 | M1(A)                   | M2(A)                 | M3(A) |
| ----------------------------- | ----------------------------- | ----------------------- | --------------------- | ----- |
| 1                             | 0                             | 15                      | 0                     | 5     |
| 1                             | 1                             | 15                      | 15                    | 10    |
| 2                             | 1                             | 30                      | 15                    | 15    |
| 2                             | 2                             | 30                      | 30                    | 20    |
| 3                             | 2                             | 45                      | 30                    | 25    |
| 3                             | 3                             | 45 Full Load Color Pink | 45                    | 30    |
| 4                             | 3                             | 0 CB6 Trip color Blue   | 45                    | 15    |
| 4                             | 4                             | 0 CB6 Trip color Blue   | 0 CB6 Trip color Blue | 0     |

The other readings in meter are for voltage and power.  
Note:- Reading of M3  
Transformer voltage ratio:- 33/11 = 3  
Hence current in primary side (33 KV) =Current in secondary side (11KV)/3  
Hence M3 Reading will be =M1+M2/3  
Whenever circuit breaker Trips , Alarm gets generated in the HMI.

</div>
