# So far what I've found out to integrate our project with Linux

1. PS_GPIO[55:24] are JA-JD. 

    JA. JA(1-4, 7-10) [24:31]
  
    JB. JB(1-4, 7-10) [32:39]
  
    JC. JC(1P, 1N, 2P, 2N, 3P, 3N, 4P, 4N) [40-47]
  
    JD. JD(1P, 1N, 2P, 2N, 3P, 3N, 4P, 4N) [48-55]
  
2. We can put our project in system.v (Verilog), the port name in system.v is processing_system7_0_GPIO [55:0], which is connected to PS_GPIO

3. The name for gclk is ```clk_100```

After adding our own project in the system.v, we just need to generate an new bitstream file. Then the integration finished. 
