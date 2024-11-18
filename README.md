
```
I DO NOT know if this will be useful, but try

ls -ltr /dev/

Which should sort the entries with the newest modification timestamps at the end of the list.  If a new entry has been created, it should (I hope) sort to the bottom of the list.  That should make it easier to identify a new entry.

Again, I do not know for sure, just hoping it works this way
```

`ls -ltr /dev/`


```
/dev system_profiler SPUSBDataType



Reply

USB:

    USB 3.1 Bus:

      Host Controller Driver: AppleT6000USBXHCI

    USB 3.1 Bus:

      Host Controller Driver: AppleT6000USBXHCI

    USB 3.1 Bus:

      Host Controller Driver: AppleT6000USBXHCI

        UVC Camera :

          Product ID: 0x017f
          Vendor ID: 0x2bdf
          Version: 0.10
          Serial Number: 530550000000100
          Speed: Up to 480 Mb/s
          Manufacturer: UVC 
          Location ID: 0x01100000 / 1
          Current Available (mA): 500
          Current Required (mA): 100
          Extra Operating Current (mA): 0
```


found this UVC tool: `git clone https://github.com/jtfrey/uvc-util.git`
```
gcc -o uvc-util -framework IOKit -framework Foundation uvc-util.m UVCController.m UVCType.m UVCValue.m
➜  src git:(master) ✗ ./uvc-util --list-devices
------------ -------------- ------------ ------------ ------------------------------------------------
Index        Vend:Prod      LocationID   UVC Version  Device name
------------ -------------- ------------ ------------ ------------------------------------------------
0            0x2bdf:0x017f  0x01100000   1.00         UVC Camera 
------------ -------------- ------------ ------------ ------------------------------------------------
```


`opreadlink -f $(brew --prefix opencv)`

```
/dev usbdiagnose
```
yields:
```
2024-11-18 09:03:35.970 usbdiagnose[79180:5632799] USB Prober: Error reading USBVendors.txt from the Resources directory
High Speed device @ 1 (0x01100000): .............................................   Miscellaneous/Common Class device: "UVC Camera "
    Port Information:   0x001a
           Not Captive
           Attached to Root Hub
           External Device
           Connected
           Enabled
    Number Of Endpoints (includes EP0):   
        Total Endpoints for Configuration 1 (current):   4
    Device Descriptor   
        Descriptor Version Number:   0x0200
        Device Class:   239   (Miscellaneous)
        Device Subclass:   2   (Common Class)
        Device Protocol:   1   (Interface Association)
        Device MaxPacketSize:   64
        Device VendorID/ProductID:   0x2BDF/0x017F   (unknown vendor)
        Device Version Number:   0x0010
        Number of Configurations:   1
        Manufacturer String:   1 "UVC "
        Product String:   2 "UVC Camera "
        Serial Number String:   3 "530550000000100"
    Configuration Descriptor (current config)   
        Length (and contents):   945
            Raw Descriptor (hex)    0000: 09 02 B1 03 04 01 00 C0  32 08 0B 00 02 0E 03 00  
            Raw Descriptor (hex)    0010: 00 09 04 00 00 01 0E 01  00 00 0D 24 01 00 01 55  
            Raw Descriptor (hex)    0020: 00 00 00 E0 01 01 01 12  24 02 01 01 02 00 00 00  
            Raw Descriptor (hex)    0030: 00 00 00 00 00 03 0A 00  00 09 24 03 02 01 01 00  
            Raw Descriptor (hex)    0040: 04 00 07 24 04 03 01 01  00 0B 24 05 04 03 00 00  
            Raw Descriptor (hex)    0050: 02 5F 17 00 1B 24 06 11  91 72 1E 9A 43 68 83 46  
            Raw Descriptor (hex)    0060: 6D 92 39 BC 79 06 EE 49  0A 01 04 02 FF 03 00 07  
            Raw Descriptor (hex)    0070: 05 85 03 40 00 01 05 25  03 40 00 09 04 01 00 01  
            Raw Descriptor (hex)    0080: 0E 02 00 00 0F 24 01 02  BB 02 81 00 02 00 00 00  
            Raw Descriptor (hex)    0090: 01 04 00 0B 24 06 01 08  00 01 00 00 00 01 1E 24  
            Raw Descriptor (hex)    00a0: 07 01 02 00 05 C0 03 00  00 00 10 00 00 00 10 00  
            Raw Descriptor (hex)    00b0: 80 25 00 15 16 05 00 01  15 16 05 00 1E 24 07 02  
            Raw Descriptor (hex)    00c0: 02 00 04 00 03 00 00 00  10 00 00 00 10 00 00 18  
            Raw Descriptor (hex)    00d0: 00 40 0D 03 00 01 40 0D  03 00 1E 24 07 03 02 00  
            Raw Descriptor (hex)    00e0: 04 58 02 00 00 00 10 00  00 00 10 00 C0 12 00 15  
            Raw Descriptor (hex)    00f0: 16 05 00 01 15 16 05 00  1E 24 07 04 02 D0 02 40  
            Raw Descriptor (hex)    0100: 02 00 00 00 10 00 00 00  10 00 A8 0C 00 15 16 05  
            Raw Descriptor (hex)    0110: 00 01 15 16 05 00 1E 24  07 05 02 80 02 00 02 00  
            Raw Descriptor (hex)    0120: 00 00 10 00 00 00 10 00  00 0A 00 15 16 05 00 01  
            Raw Descriptor (hex)    0130: 15 16 05 00 1E 24 07 06  02 80 02 E0 01 00 00 00  
            Raw Descriptor (hex)    0140: 10 00 00 00 10 00 60 09  00 15 16 05 00 01 15 16  
            Raw Descriptor (hex)    0150: 05 00 1E 24 07 07 02 40  01 F0 00 00 00 00 10 00  
            Raw Descriptor (hex)    0160: 00 00 10 00 58 02 00 15  16 05 00 01 15 16 05 00  
            Raw Descriptor (hex)    0170: 1E 24 07 08 02 78 00 A0  00 00 00 00 10 00 00 00  
            Raw Descriptor (hex)    0180: 10 00 96 00 00 15 16 05  00 01 15 16 05 00 06 24  
            Raw Descriptor (hex)    0190: 0D 00 00 00 1C 24 10 02  08 48 32 36 34 00 00 10  
            Raw Descriptor (hex)    01a0: 00 80 00 00 AA 00 38 9B  71 18 01 00 00 00 01 01  
            Raw Descriptor (hex)    01b0: 1E 24 11 01 02 00 05 C0  03 00 00 00 10 00 00 00  
            Raw Descriptor (hex)    01c0: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 1E 24  
            Raw Descriptor (hex)    01d0: 11 02 02 00 04 00 03 00  00 00 10 00 00 00 10 40  
            Raw Descriptor (hex)    01e0: 0D 03 00 01 00 00 00 00  40 0D 03 00 1E 24 11 03  
            Raw Descriptor (hex)    01f0: 02 00 04 58 02 00 00 00  10 00 00 00 10 15 16 05  
            Raw Descriptor (hex)    0200: 00 01 00 00 00 00 15 16  05 00 1E 24 11 04 02 D0  
            Raw Descriptor (hex)    0210: 02 40 02 00 00 00 10 00  00 00 10 15 16 05 00 01  
            Raw Descriptor (hex)    0220: 00 00 00 00 15 16 05 00  1E 24 11 05 02 80 02 00  
            Raw Descriptor (hex)    0230: 02 00 00 00 10 00 00 00  10 15 16 05 00 01 00 00  
            Raw Descriptor (hex)    0240: 00 00 15 16 05 00 1E 24  11 06 02 80 02 E0 01 00  
            Raw Descriptor (hex)    0250: 00 00 10 00 00 00 10 15  16 05 00 01 00 00 00 00  
            Raw Descriptor (hex)    0260: 15 16 05 00 1E 24 11 07  02 40 01 F0 00 00 00 00  
            Raw Descriptor (hex)    0270: 10 00 00 00 10 15 16 05  00 01 00 00 00 00 15 16  
            Raw Descriptor (hex)    0280: 05 00 1E 24 11 08 02 78  00 A0 00 00 00 00 10 00  
            Raw Descriptor (hex)    0290: 00 00 10 15 16 05 00 01  00 00 00 00 15 16 05 00  
            Raw Descriptor (hex)    02a0: 06 24 0D 00 00 00 1B 24  04 03 04 59 55 59 32 00  
            Raw Descriptor (hex)    02b0: 00 10 00 80 00 00 AA 00  38 9B 71 10 02 00 00 00  
            Raw Descriptor (hex)    02c0: 00 1E 24 05 01 00 00 05  D0 02 00 00 E0 2E 00 00  
            Raw Descriptor (hex)    02d0: E0 2E 00 00 32 00 15 16  05 00 01 15 16 05 00 1E  
            Raw Descriptor (hex)    02e0: 24 05 02 00 80 02 E0 01  00 00 B8 0B 00 00 B8 0B  
            Raw Descriptor (hex)    02f0: 00 80 0C 00 15 16 05 00  01 15 16 05 00 1E 24 05  
            Raw Descriptor (hex)    0300: 03 00 80 02 00 02 00 00  B8 0B 00 00 B8 0B 00 80  
            Raw Descriptor (hex)    0310: 0C 00 15 16 05 00 01 15  16 05 00 1E 24 05 04 00  
            Raw Descriptor (hex)    0320: 80 02 00 01 00 00 B8 0B  00 00 B8 0B 00 80 0C 00  
            Raw Descriptor (hex)    0330: 15 16 05 00 01 15 16 05  00 06 24 0D 00 00 00 07  
            Raw Descriptor (hex)    0340: 05 81 02 00 02 00 08 0B  02 02 01 02 00 00 09 04  
            Raw Descriptor (hex)    0350: 02 00 00 01 01 00 00 09  24 01 00 01 26 00 01 03  
            Raw Descriptor (hex)    0360: 0C 24 02 01 01 02 00 02  03 00 00 00 09 24 03 02  
            Raw Descriptor (hex)    0370: 01 01 00 03 00 08 24 06  03 01 01 03 00 09 04 03  
            Raw Descriptor (hex)    0380: 00 00 01 02 00 00 09 04  03 01 01 01 02 00 00 07  
            Raw Descriptor (hex)    0390: 24 01 02 FF 01 00 0B 24  02 01 02 02 10 01 80 3E  
            Raw Descriptor (hex)    03a0: 00 09 05 83 0D 44 00 04  00 00 07 25 01 01 01 4D  
            Raw Descriptor (hex)    03b0: 01 
        Number of Interfaces:   4
        Configuration Value:   1
        Attributes:   0xC0 (self-powered)
        MaxPower:   100 mA
        Interface Association   Video/Interface Collection
            First Interface   0
            Interface Count   2
            Function Class   14   (Video)
            Function Subclass   3   (Interface Collection)
            Interface Protocol   0
            Function String   0 (none)
        Interface #0 - Video/Control   
            Alternate Setting   0
            Number of Endpoints   1
            Interface Class:   14   (Video)
            Interface Subclass;   1   (Control)
            Interface Protocol:   0
            VDC (Control) Header   
                Length (and contents):   13
                    Raw Descriptor (hex)   0000: 0D 24 01 00 01 55 00 00  00 E0 01 01 01 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x1
                Specification Version Number:   01.0
                Device Clock Frequency (Hz):   31457280
                Number of Video Streaming Interfaces:   1
                Video Interface Number:   1
            VDC (Control) Input Terminal   
                Length (and contents):   18
                    Raw Descriptor (hex)    0000: 12 24 02 01 01 02 00 00  00 00 00 00 00 00 03 0A  
                    Raw Descriptor (hex)    0010: 00 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x2
                bTerminalID:   1
                wTerminalType:   0x201 (ITT_CAMERA)
                bAssocTerminal:   0 [NONE]
                iTerminal:   0 [NONE]
                wObjectiveFocalLengthMin:   0
                wObjectiveFocalLengthMax:   0
                wOcularFocalLength:   0
                Controls Supported   Description
                       Auto Exposure Mode
                       Exposure Time (Absolute)
            VDC (Control) Output Terminal   
                Length (and contents):   9
                    Raw Descriptor (hex)   0000: 09 24 03 02 01 01 00 04  00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x3
                bTerminalID:   2
                wTerminalType:   0x101 (TT_STREAMING)
                bAssocTerminal:   0 [NONE]
                bSourceID:   4
                iTerminal:   0 [NONE]
            VDC (Control) Selector Unit   
                Length (and contents):   7
                    Raw Descriptor (hex)   0000: 07 24 04 03 01 01 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x4
                Unit ID:   3
                Number of pins:   1
                Source ID Pin[0]:   1
                Selector Unit String Index:   0 [NONE]
            VDC (Control) Processing Unit   
                Length (and contents):   11
                    Raw Descriptor (hex)   0000: 0B 24 05 04 03 00 00 02  5F 17 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x5
                Unit ID:   4
                Source ID:   3
                Digital Multiplier (100X):   0
                Controls Supported   Description
                       Brightness
                       Contrast
                       Hue
                       Saturation
                       Sharpness
                       White Balance Temperature
                       Backlight Compensation
                       Gain
                       Power Line Frequency
                       White Balance Temperature, Auto
                Processing Unit String Index:   0 [NONE]
            VDC (Control) Extension Unit   
                Length (and contents):   27
                    Raw Descriptor (hex)    0000: 1B 24 06 11 91 72 1E 9A  43 68 83 46 6D 92 39 BC  
                    Raw Descriptor (hex)    0010: 79 06 EE 49 0A 01 04 02  FF 03 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x6
                bLength:   27
                bDescriptorType:   36
                bDescriptorSubType:   6
                Unit ID:   17
                Vendor UUID:   9a1e7291-6843-4683-6d92-39bc7906ee49
                Number of Controls:   10
                Number of In pins:   1
                Source ID Pin[0]:   4
                Controls Supported   Description
                       Vendor Specific Byte[i] = 0xff
                       Vendor Specific Byte[i] = 0x3
                Processing Unit String Index:   0 [NONE]
            Endpoint 0x85 - Interrupt Input   
                Address:   0x85  (IN)
                Attributes:   0x03  (Interrupt)
                Max Packet Size:   0x0040  (64 x 1  transactions opportunities per microframe)
                Polling Interval:   1 (1 microframe (125 microsecs) )
            VDC Specific Interrupt Endpoint   
                Length (and contents):   5
                    Raw Descriptor (hex)   0000: 05 25 03 40 00 
                Max Transfer Size:   64
        Interface #1 - Video/Streaming   
            Alternate Setting   0
            Number of Endpoints   1
            Interface Class:   14   (Video)
            Interface Subclass;   2   (Streaming)
            Interface Protocol:   0
            VDC (Streaming) Input Header   
                Length (and contents):   15
                    Raw Descriptor (hex)   0000: 0F 24 01 02 BB 02 81 00  02 00 00 00 01 04 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x1
                bNumFormats:   2
                wTotalLength:   0x2bb (699)
                bEndpointAddress:   0x81
                Capabilities (0x0)   bmInfo
                bTerminalLink:   2
                bStillCaptureMethod:   0 (None)
                bTriggerSupport   0 (Not Supported)
                bTriggerUsage   Ignored because bTriggerSupport is 0
                bControlSize:   0x1
                bmaControls( Format 1):   0x4
                       Compression quality
                bmaControls( Format 2):   0x4
                       Compression quality
            VDC (Streaming) MJPEG Format Descriptor   
                Length (and contents):   11
                    Raw Descriptor (hex)   0000: 0B 24 06 01 08 00 01 00  00 00 01 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x6
                bFormatIndex:   0x1
                bNumFrameDescriptors:   0x8
                bmFlags   (0x0)
                bDefaultFrameIndex:   0x1
                bAspectRatioX:   0x0
                bAspectRatioY:   0x0
                bmInterlaceFlags   (0x0)
                    Interlaced Stream or Variable   No
                    Fields per frame   1
                    Field 1 first   No
                    Field Pattern   Field 1 only
                    Display Mode   Bob only
                bCopyProtect:   Restricted
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 01 02 00 05 C0  03 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 80 25 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   1
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x500 (1280)
                wHeight:   0x3c0 (960)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x258000 (2457600)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 02 02 00 04 00  03 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 00 18 00 40 0D 03  00 01 40 0D 03 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   2
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x400 (1024)
                wHeight:   0x300 (768)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x180000 (1572864)
                dwDefaultFrameInterval:   0x30d40 (  20.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x30d40 (  20.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 03 02 00 04 58  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 C0 12 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   3
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x400 (1024)
                wHeight:   0x258 (600)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x12c000 (1228800)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 04 02 D0 02 40  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 A8 0C 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   4
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x2d0 (720)
                wHeight:   0x240 (576)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0xca800 (829440)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 05 02 80 02 00  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 00 0A 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   5
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x280 (640)
                wHeight:   0x200 (512)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0xa0000 (655360)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 06 02 80 02 E0  01 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 60 09 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   6
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x280 (640)
                wHeight:   0x1e0 (480)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x96000 (614400)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 07 02 40 01 F0  00 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 58 02 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   7
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x140 (320)
                wHeight:   0xf0 (240)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x25800 (153600)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) MJPEG Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 07 08 02 78 00 A0  00 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 00 96 00 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x7
                bFrameIndex:   8
                bmCapabilities    (0x2)
                       Unknown capabilities
                wWidth:   0x78 (120)
                wHeight:   0xa0 (160)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwMaxVideoFrameBufferSize (bytes):   0x9600 (38400)
                dwDefaultFrameInterval:   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) Color Format Descriptor   
                Length (and contents):   6
                    Raw Descriptor (hex)   0000: 06 24 0D 00 00 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0xd
                Color Primaries:   0 ( Unspecified (Image characteristic unknown) )
                Transfer Characteristics:   0 ( Unspecified (Image characteristic unknown) )
                Matrix Coefficients:   0 ( Unspecified (Image characteristic unknown) )
            VDC (Streaming) Frame-Based Format Descriptor   
                Length (and contents):   28
                    Raw Descriptor (hex)    0000: 1C 24 10 02 08 48 32 36  34 00 00 10 00 80 00 00  
                    Raw Descriptor (hex)    0010: AA 00 38 9B 71 18 01 00  00 00 01 01 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x10
                bFormatIndex:   0x2
                bNumFrameDescriptors:   0x8
                Format GUID:   34363248-0000-0010-8000-00aa00389b71
                bBitsPerPixel:   0x18 (24)
                bDefaultFrameIndex:   0x1
                bAspectRatioX:   0x0
                bAspectRatioY:   0x0
                bmInterlaceFlags   (0x0)
                    Interlace Stream or variable   NO
                    Fields per Frame   2
                    Field 1 First   No
                    Field Pattern   Field 1 only
                Copy Protection:   Restrict Duplication
                bVariableSize:   0x1
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 01 02 00 05 C0  03 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x1
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x500 (1280)
                wHeight:   0x3c0 (960)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x40002 (  26.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 02 02 00 04 00  03 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 40 0D 03 00 01 00 00  00 00 40 0D 03 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x2
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x400 (1024)
                wHeight:   0x300 (768)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x30d40 (  20.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x58040002 (147665.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 03 02 00 04 58  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x3
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x400 (1024)
                wHeight:   0x258 (600)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x4002d002 (107392.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 04 02 D0 02 40  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x4
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x2d0 (720)
                wHeight:   0x240 (576)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x28002 (  16.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 05 02 80 02 00  02 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x5
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x280 (640)
                wHeight:   0x200 (512)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0xe0028002 (375826.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 06 02 80 02 E0  01 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x6
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x280 (640)
                wHeight:   0x1e0 (480)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0xf0014002 (402661.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 07 02 40 01 F0  00 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x7
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x140 (320)
                wHeight:   0xf0 (240)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0xa0007802 (268438.000 ms)
            VDC (Streaming) Frame-Based Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 11 08 02 78 00 A0  00 00 00 00 10 00 00 00  
                    Raw Descriptor (hex)    0010: 10 15 16 05 00 01 00 00  00 00 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x11
                bFrameIndex:   0x8
                bmCapabilities    (0x2)
                       Fixed Frame Rate
                       Unknown capabilities
                wWidth:   0x78 (120)
                wHeight:   0xa0 (160)
                dwMinBitRate (bps):   0x10000000 (268435456)
                dwMaxBitRate (bps):   0x10000000 (268435456)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                dwBytesPerLine:   0x0 (0)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x241b0000 (60574.000 ms)
            VDC (Streaming) Color Format Descriptor   
                Length (and contents):   6
                    Raw Descriptor (hex)   0000: 06 24 0D 00 00 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0xd
                Color Primaries:   0 ( Unspecified (Image characteristic unknown) )
                Transfer Characteristics:   0 ( Unspecified (Image characteristic unknown) )
                Matrix Coefficients:   0 ( Unspecified (Image characteristic unknown) )
            VDC (Streaming) Uncompressed Format Descriptor   
                Length (and contents):   27
                    Raw Descriptor (hex)    0000: 1B 24 04 03 04 59 55 59  32 00 00 10 00 80 00 00  
                    Raw Descriptor (hex)    0010: AA 00 38 9B 71 10 02 00  00 00 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x4
                bFormatIndex:   0x3
                bNumFrameDescriptors:   0x4
                Format GUID:   32595559-0000-0010-8000-00aa00389b71
                bBitsPerPixel:   0x10 (16)
                bDefaultFrameIndex:   0x2
                bAspectRatioX:   0x0
                bAspectRatioY:   0x0
                bmInterlaceFlags   (0x0)
                    Interlace Stream or variable   NO
                    Fields per Frame   2
                    Field 1 First   No
                    Field Pattern   Field 1 only
                    Display Mode   Bob only
                Copy Protection:   No Restrictions
            VDC (Streaming) Uncompressed Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 05 01 00 00 05 D0  02 00 00 E0 2E 00 00 E0  
                    Raw Descriptor (hex)    0010: 2E 00 00 32 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x5
                bFrameIndex:   0x1
                bmCapabilities    (0x0)
                wWidth:   0x500 (1280)
                wHeight:   0x2d0 (720)
                dwMinBitRate (bps):   0x2ee00000 (786432000)
                dwMaxBitRate (bps):   0x2ee00000 (786432000)
                dwMaxVideoFrameBufferSize (bytes):   0x320000 (3276800)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) Uncompressed Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 05 02 00 80 02 E0  01 00 00 B8 0B 00 00 B8  
                    Raw Descriptor (hex)    0010: 0B 00 80 0C 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x5
                bFrameIndex:   0x2
                bmCapabilities    (0x0)
                wWidth:   0x280 (640)
                wHeight:   0x1e0 (480)
                dwMinBitRate (bps):   0xbb80000 (196608000)
                dwMaxBitRate (bps):   0xbb80000 (196608000)
                dwMaxVideoFrameBufferSize (bytes):   0xc8000 (819200)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) Uncompressed Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 05 03 00 80 02 00  02 00 00 B8 0B 00 00 B8  
                    Raw Descriptor (hex)    0010: 0B 00 80 0C 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x5
                bFrameIndex:   0x3
                bmCapabilities    (0x0)
                wWidth:   0x280 (640)
                wHeight:   0x200 (512)
                dwMinBitRate (bps):   0xbb80000 (196608000)
                dwMaxBitRate (bps):   0xbb80000 (196608000)
                dwMaxVideoFrameBufferSize (bytes):   0xc8000 (819200)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) Uncompressed Frame Descriptor   
                Length (and contents):   30
                    Raw Descriptor (hex)    0000: 1E 24 05 04 00 80 02 00  01 00 00 B8 0B 00 00 B8  
                    Raw Descriptor (hex)    0010: 0B 00 80 0C 00 15 16 05  00 01 15 16 05 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x5
                bFrameIndex:   0x4
                bmCapabilities    (0x0)
                wWidth:   0x280 (640)
                wHeight:   0x100 (256)
                dwMinBitRate (bps):   0xbb80000 (196608000)
                dwMaxBitRate (bps):   0xbb80000 (196608000)
                dwMaxVideoFrameBufferSize (bytes):   0xc8000 (819200)
                dwDefaultFrameInterval (100 ns):   0x51615 (  33.000 ms)
                Discrete Frame Intervals supported   0x1
                    dwFrameInterval[1] (100 ns)   0x51615 (  33.000 ms)
            VDC (Streaming) Color Format Descriptor   
                Length (and contents):   6
                    Raw Descriptor (hex)   0000: 06 24 0D 00 00 00 
                bDescriptorType:   0x24
                bDescriptorSubType:   0xd
                Color Primaries:   0 ( Unspecified (Image characteristic unknown) )
                Transfer Characteristics:   0 ( Unspecified (Image characteristic unknown) )
                Matrix Coefficients:   0 ( Unspecified (Image characteristic unknown) )
            Endpoint 0x81 - Bulk Input   
                Address:   0x81  (IN)
                Attributes:   0x02  (Bulk)
                Max Packet Size:   512
                Polling Interval:   0 ( Endpoint never NAKs)
        Interface Association   Audio/Streaming
            First Interface   2
            Interface Count   2
            Function Class   1   (Audio)
            Function Subclass   2   (Streaming)
            Interface Protocol   0
            Function String   0 (none)
        Interface #2 - Audio/Control   
            Alternate Setting   0
            Number of Endpoints   0
            Interface Class:   1   (Audio)
            Interface Subclass;   1   (Control)
            Interface Protocol:   0
            Audio Class 1.0 Control Interface   
                Descriptor Version Number:   01.00
                Class Specific Size:   38
                Number of Audio Interfaces:   1
                Audio Interface Number:   3
                Dump Contents (hex):   09 24 01 00 01 26 00 01 03 
            Audio Class 1.0 Input Terminal   
                Terminal ID:   1
                Input Terminal Type:   0x201 (Microphone)
                OutTerminal ID:   0 [NONE]
                Number of Channels:   2
                Spatial config of channels:   0000000000000011
                                  ^.  Left Front
                                 ^..  Right Front
                String index for first logical channel:   0
                Terminal Name String Index:   0 [NONE]
            Audio Class 1.0 Output Terminal   
                Terminal ID:   2
                Output Terminal Type:   0x101 (USB Isochronous Stream)
                InTerminal ID:   0 [NONE]
                Source ID:   3
                Terminal Name String Index:   0 [NONE]
            Audio Class 1.0 Feature Unit   
                Unit ID:   3
                Source ID:   1
                Control Size:   1
                Number of Channels (ch):   0
                    Master Channel:......................... ( Volume, Mute )
                Feature Unit Name String Index:   0
                Dump Contents (hex):   08 24 06 03 01 01 03 00 
        Interface #3 - Audio/Streaming   
            Alternate Setting   0
            Number of Endpoints   0
            Interface Class:   1   (Audio)
            Interface Subclass;   2   (Streaming)
            Interface Protocol:   0
        Interface #3 - Audio/Streaming (#1)   
            Alternate Setting   1
            Number of Endpoints   1
            Interface Class:   1   (Audio)
            Interface Subclass;   2   (Streaming)
            Interface Protocol:   0
            Audio Class 1.0 Streaming Interface   
                Audio Class 1.0 Streaming Interface   
                    Endpoint Terminal ID:   2
                    Delay:   255 frames     
                    Format Tag:   0x0001 (PCM)
            Audio Class 1.0 Streaming Format Type   
                Audio Class 1.0 Stream Format Type Desc.   
                    Format Type:   1 PCM
                    Number Of Channels:   2 STEREO
                    Sub Frame Size:   2
                    Bit Resolution:   16
                    Sample Frequency Type:   0x01 (Discrete)
                    Sample Frequency:   16000 Hz
            Endpoint 0x83 - Isochronous Input   
                Address:   0x83  (IN)
                Attributes:   0x0D  (Isochronous synchronous data endpoint)
                Max Packet Size:   0x0044  (68 x 1  transactions opportunities per microframe)
                Polling Interval:   4 (8 microframes (1 msecs) )
            Class-Specific AS Audio EndPoint   
                Attributes:   0x01  Sample Frequency,  
                bLockDelayUnits:   0x01  (Milliseconds)
                wLockDelay:   333 ms
    Device Qualifier Descriptor   
        Descriptor Version Number:   0x0200
        Device Class   239   (Miscellaneous)
        Device Subclass   2   (Common Class)
        Device Protocol   1   (Interface Association)
        Device MaxPacketSize:   64
        Number of Configurations:   1
        bReserved:   0
    Other Speed Configuration Descriptor   
        Length (and contents):   464
            Raw Descriptor (hex)    0000: 09 07 D0 01 0A 01 00 C0  32 08 0B 00 02 0E 03 00  
            Raw Descriptor (hex)    0010: 00 09 04 00 00 01 0E 01  00 00 0D 24 01 00 01 55  
            Raw Descriptor (hex)    0020: 00 00 00 E0 01 01 01 12  24 02 01 01 02 00 00 00  
            Raw Descriptor (hex)    0030: 00 00 00 00 00 03 0A 00  09 24 03 02 01 01 00 04  
            Raw Descriptor (hex)    0040: 00 07 24 04 03 01 01 00  0B 24 05 04 03 00 00 03  
            Raw Descriptor (hex)    0050: 5F 17 00 07 05 83 03 40  00 01 05 25 03 40 00 09  
            Raw Descriptor (hex)    0060: 04 01 00 01 0E 02 00 00  07 05 81 01 FE 01 01 0E  
            Raw Descriptor (hex)    0070: 24 01 01 5A 01 81 00 02  03 00 00 01 04 1C 24 10  
            Raw Descriptor (hex)    0080: 01 08 48 32 36 34 00 00  10 00 80 00 00 AA 00 38  
            Raw Descriptor (hex)    0090: 9B 71 18 01 00 00 00 00  01 26 24 11 01 00 00 05  
            Raw Descriptor (hex)    00a0: D0 02 00 00 00 02 00 00  00 10 15 16 05 00 00 00  
            Raw Descriptor (hex)    00b0: 00 00 00 15 16 05 00 15  16 05 00 0B 8B 02 00 26  
            Raw Descriptor (hex)    00c0: 24 11 02 00 00 04 00 03  00 00 00 02 00 00 00 10  
            Raw Descriptor (hex)    00d0: 15 16 05 00 00 00 00 00  00 15 16 05 00 15 16 05  
            Raw Descriptor (hex)    00e0: 00 0B 8B 02 00 26 24 11  03 00 80 02 E0 01 00 00  
            Raw Descriptor (hex)    00f0: 00 02 00 00 00 10 15 16  05 00 00 00 00 00 00 15  
            Raw Descriptor (hex)    0100: 16 05 00 15 16 05 00 0B  8B 02 00 26 24 11 04 00  
            Raw Descriptor (hex)    0110: 40 01 F0 00 00 00 00 02  00 00 00 10 15 16 05 00  
            Raw Descriptor (hex)    0120: 00 00 00 00 00 15 16 05  00 15 16 05 00 0B 8B 02  
            Raw Descriptor (hex)    0130: 00 26 24 11 05 00 00 04  40 02 00 00 00 02 00 00  
            Raw Descriptor (hex)    0140: 00 10 15 16 05 00 00 00  00 00 00 15 16 05 00 15  
            Raw Descriptor (hex)    0150: 16 05 00 0B 8B 02 00 26  24 11 06 00 20 03 58 02  
            Raw Descriptor (hex)    0160: 00 00 00 02 00 00 00 10  15 16 05 00 00 00 00 00  
            Raw Descriptor (hex)    0170: 00 15 16 05 00 15 16 05  00 0B 8B 02 00 26 24 11  
            Raw Descriptor (hex)    0180: 07 00 20 03 E0 01 00 00  00 02 00 00 00 10 15 16  
            Raw Descriptor (hex)    0190: 05 00 00 00 00 00 00 15  16 05 00 15 16 05 00 0B  
            Raw Descriptor (hex)    01a0: 8B 02 00 26 24 11 08 00  80 02 68 01 00 00 00 02  
            Raw Descriptor (hex)    01b0: 00 00 00 10 15 16 05 00  00 00 00 00 00 15 16 05  
            Raw Descriptor (hex)    01c0: 00 15 16 05 00 0B 8B 02  00 06 24 0D 00 00 00 00  
            Unknown Descriptor   01d0: 
        Number of Interfaces:   10
        Configuration Value:   1
        Attributes:   0xC0 (self-powered)
        MaxPower:   100 mA
        Interface Association   Video/Interface Collection
            First Interface   0
            Interface Count   2
            Function Class   14   (Video)
            Function Subclass   3   (Interface Collection)
            Interface Protocol   0
            Function String   0 (none)
        Interface #0 - Video/Control   
            Alternate Setting   0
            Number of Endpoints   1
            Interface Class:   14   (Video)
            Interface Subclass;   1   (Control)
            Interface Protocol:   0
            VDC (Control) Header   
                Length (and contents):   13
                    Raw Descriptor (hex)   0000: 0D 24 01 00 01 55 00 00  00 E0 01 01 01 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x1
                Specification Version Number:   01.0
                Device Clock Frequency (Hz):   31457280
                Number of Video Streaming Interfaces:   1
                Video Interface Number:   1
            VDC (Control) Input Terminal   
                Length (and contents):   18
                    Raw Descriptor (hex)    0000: 12 24 02 01 01 02 00 00  00 00 00 00 00 00 03 0A  
                    Raw Descriptor (hex)    0010: 00 09 
                bDescriptorType:   0x24
                bDescriptorSubType:   0x2
                bTerminalID:   1
                wTerminalType:   0x201 (ITT_CAMERA)
                bAssocTerminal:   0 [NONE]
                iTerminal:   0 [NONE]
                wObjectiveFocalLengthMin:   0
                wObjectiveFocalLengthMax:   0
                wOcularFocalLength:   0
                Controls Supported   Description
                       Auto Exposure Mode
                       Exposure Time (Absolute)
                       Reserved
                       Reserved
        Illegal Descriptor:   Length of 0
```
