# speedtest
The purpose of this repository is to measure our connection speed without 3rd party tools, using our beloved [wget](https://www.gnu.org/software/wget/).

This repository has files with different sizes.
The optimum file size to download to measure download speed depends on the speed of your internet connection and the purpose of the measurement. Here are some general guidelines:
- 10 MB: Slow internet connection, such as a dial-up connection.
- 100 MB: Moderate internet connection, such as a DSL or cable connection.
- 1000 MB: Fast internet connection, such as fiber optic or gigabit connection.

Results should be similar to speed test services like [nPerf](https://www.nperf.com)
## Download speed
`wget -O /dev/null https://github.com/juanmancebo/speedtest/raw/main/1000MB --report-speed=bits 2>&1 |tail -2 |head -1|cut -d \( -f2 |cut -d \) -f1`
## Latency
`echo $(ping -c 50 $(wget -qO- ifconfig.me) | tail -1 | awk '{print $4}' | cut -d '/' -f2) ms`
