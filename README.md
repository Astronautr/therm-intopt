# thermocompensation
Application of interval optimization to thermocompensation

Build instruction:
cd ${THERMOCOMPENSATION}/java
mvn clean install

File example/P.csv contains data for 8 devices.
It contains 4 columns:
- chipNo    device id;
- temp      temperature sensor;
- out       required output of polynom evaluator
- freq      measured frequency used only for output

Run instruction:
cd ${THERMOCOMPENSATION}/java/optim
mvn exec:exec

Expected output:
1:  0 23 75 0 13 3 6 0 0 0 7 # f = 12002943 +- 35
2:  17 16 107 0 21 0 8 0 0 0 7 # f = 12003021 +- 18
3:  10 22 62 0 12 4 5 0 0 0 7 # f = 12003022 +- 44
4:  16 24 102 0 16 19 0 0 0 0 7 # f = 12002942 +- 22
5:  4 25 52 0 7 6 5 0 0 0 7 # f = 12002955 +- 37
6:  21 15 119 1 26 0 8 0 0 0 7 # f = 12002816 +- 15
7:  11 16 118 3 27 2 6 0 0 0 7 # f = 12002968 +- 22
8:  15 19 89 0 16 4 6 0 0 0 7 # f = 12002933 +- 26
chipNo: coefficients # f = freq +- delta
- chipNo        device id;
- coefficients  coefficients returned by optimization
- freq          average frequency
- delta         maximal delta between requred output and
                actual output for found coefficients.

