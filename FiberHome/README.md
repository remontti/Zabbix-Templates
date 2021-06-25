
RP700 Firmware:

```bash
Admin# cd device
Admin\device# set mib performance switch enable
Admin# cd gponlinecard
Admin\gponlinecard# set pon_traffic_sts switch opt enable 5 0 rtt enable 5 0 traffic enable 5 0
```

RP1000/1200 Firmware:
```bash
Admin# cd maintenance
Admin\maintenance# cd performance
Admin\maintenance\performance# set mib performance switch enable
Admin\maintenance\performance# show mib performance switch 
Mib performance switch is enable.
Admin\maintenance\performance# set pon_traffic_sts switch opt enable 5 0 rtt enable 5 0 traffic enable 5 0
Admin\maintenance\performance# show pon_traffic_sts switch 
Pon_traffic_sort_swicth cfg:
Traffic cfg: switch:enable, interval:5, report_delaytime:0 
Onu_rttval cfg: switch:enable, interval:5, report_delaytime:0 
Opt_pwr cfg: switch:enable, interval:5, report_delaytime:0
```
