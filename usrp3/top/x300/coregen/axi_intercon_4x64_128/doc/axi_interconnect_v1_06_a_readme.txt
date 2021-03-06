CHANGE LOG for AXI Interconnect V1.06.a

================================================================================

This document contains the following sections: 

1. Introduction
2. New Features
3. Supported Devices
4. Resolved Issues
5. Known Issues 
6. Technical Support
7. Core Release History
8. Legal Disclaimer
 
================================================================================
 
1. INTRODUCTION

For installation instructions for this release, please go to:

   www.xilinx.com/ipcenter/coregen/ip_update_install_instructions.htm

For system requirements:

   www.xilinx.com/ipcenter/coregen/ip_update_system_requirements.htm


2. SUPPORTED DEVICES

  The following device families are supported by the core for this release.
  
  2.1 ISE

    All 7 Series devices
    Zynq-7000 devices
    All Virtex-6 devices
    All Spartan-6 devices

  2.2 Vivado

    All 7 Series devices
    Zynq-7000 devices


3. NEW FEATURES  

   14.1 / 2012.1:
 
   -  Synchronous clock-domain crossings are performed completely within the clock converter module, 
      so multi-cycle clock constraints are no longer necessary and are no longer generated. 
      ACLK period parameter is used only for async clock conversions, and the async CDC clock constraints 
      will still succeed using a TIG, even if the ACLK period is not specified.
      
   -  Asynchronous clock-domain crossings are now performed using a single instance of 5-channel 
      AXI FIFO (per interface slot) instead of 5 separate calls to fifo_generator, thereby decreasing compilation time.
      Timing constraints for async CDC are now conditionally generated only if the interconnect instance performs any 
      async conversions.


4. RESOLVED ISSUES 

   14.4 / 2012.4:
 
   -  When using the Vivado implementation flow, the axi_interconnect core generates XDC timing constraints for each 
      asynchronous clock-domain crossing. Beginning in 14.4, these timing constraints are based on clock periods defined 
      in your system-level XDC (using create_clock). If a system-level clock definition is missing for the AXI ACLK pin 
      on either side of any async conversion, implementation will issue critical warnings.

5. KNOWN ISSUES 

   The following are known issues for v1.06.a of this core at time of release:
   
   - Setting parameter C_S_AXI_IS_INTERCONNECT = 1 is not supported.
   
   - The diagnostic control interface (S_AXI_CTRL) is not implemented. The parameter 
     C_USE_CTRL_PORT is therefore forced to 0.


6. TECHNICAL SUPPORT 

   To obtain technical support, create a WebCase at www.xilinx.com/support.
   Questions are routed to a team with expertise using this product.  
     
   Xilinx provides technical support for use of this product when used
   according to the guidelines described in the core documentation, and
   cannot guarantee timing, functionality, or support of this product for
   designs that do not follow specified guidelines.


7. CORE RELEASE HISTORY 

Date        By            Version      Description
================================================================================
04/24/2012  Xilinx, Inc.  1.06.a       ISE 14.1 and Vivado 2012.1; Defense Grade 7 Series and Zynq devices, Automotive Zynq devices.
01/19/2012  Xilinx, Inc.  1.05.a       ISE 13.4: Minor feature enhancements, completely backward-compatible.
08/19/2011  Xilinx, Inc.  1.04.a       ISE 13.3: Minor feature enhancements, completely backward-compatible.
06/22/2011  Xilinx, Inc.  1.03.a       ISE 13.2: CORE Generator tool flow support
03/01/2011  Xilinx, Inc.  1.02.a       EDK 13.1: Deployed using only the XPS tool flow
================================================================================

8. Legal Disclaimer

 (c) Copyright 2002 - 2012 Xilinx, Inc. All rights reserved.

 This file contains confidential and proprietary information
 of Xilinx, Inc. and is protected under U.S. and
 international copyright and other intellectual property
 laws.
 
 DISCLAIMER
 This disclaimer is not a license and does not grant any
 rights to the materials distributed herewith. Except as
 otherwise provided in a valid license issued to you by
 Xilinx, and to the maximum extent permitted by applicable
 law: (1) THESE MATERIALS ARE MADE AVAILABLE "AS IS" AND
 WITH ALL FAULTS, AND XILINX HEREBY DISCLAIMS ALL WARRANTIES
 AND CONDITIONS, EXPRESS, IMPLIED, OR STATUTORY, INCLUDING
 BUT NOT LIMITED TO WARRANTIES OF MERCHANTABILITY, NON-
 INFRINGEMENT, OR FITNESS FOR ANY PARTICULAR PURPOSE; and
 (2) Xilinx shall not be liable (whether in contract or tort,
 including negligence, or under any other theory of
 liability) for any loss or damage of any kind or nature
 related to, arising under or in connection with these
 materials, including for any direct, or any indirect,
 special, incidental, or consequential loss or damage
 (including loss of data, profits, goodwill, or any type of
 loss or damage suffered as a result of any action brought
 by a third party) even if such damage or loss was
 reasonably foreseeable or Xilinx had been advised of the
 possibility of the same.
 
 CRITICAL APPLICATIONS
 Xilinx products are not designed or intended to be fail-
 safe, or for use in any application requiring fail-safe
 performance, such as life-support or safety devices or
 systems, Class III medical devices, nuclear facilities,
 applications related to the deployment of airbags, or any
 other applications that could lead to death, personal
 injury, or severe property or environmental damage
 (individually and collectively, "Critical
 Applications"). Customer assumes the sole risk and
 liability of any use of Xilinx products in Critical
 Applications, subject only to applicable laws and
 regulations governing limitations on product liability.
 
 THIS COPYRIGHT NOTICE AND DISCLAIMER MUST BE RETAINED AS
 PART OF THIS FILE AT ALL TIMES.
