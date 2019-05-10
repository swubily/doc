Subject:

 FW: MMS regeneration tool share

From:

 Wang, Kelly (NSN - CN/Cheng Du)

To:

 Zhou, Celia (NSN - CN/Cheng Du); Wang, Zhangchuan (NSN - CN/Cheng Du); Li, Yi 3. (NSN - CN/Cheng Du)

Date Sent:

 9/13/2013 5:55:09 PM

Hi, All

FYI, hope it can help

Thanks

Br, Kelly



_____________________________________________
**From:** Wang, Kelly (NSN - CN/Cheng Du)
**Sent:** Monday, December 31, 2012 3:54 PM
**To:** Guo, David (NSN - CN/Cheng Du)
**Cc:** Zhai, Xiangyong (NSN - CN/Cheng Du)
**Subject:** MMS regeneration tool share





Hi, David

I’d like to share a small tool here. In case resolving process, once we get some mm1 or mm7 mms with problem and not easy to reproduce it in customer’s environment, we can use this tool to send the captured mms to our lab server, this can help to facilitate the case resolving procedure.

The first attachment is the slides introducing how to export raw file from a cap file



The second attachment is the tool to send the extracted raw file to MMSC by using the command below:

root> cat your_raw_file|./packet_send.pl hostname port



Please share it to the guys who need it. Hope it can be helpful in the future work.

Thanks

Thanks

Br, Kelly

![img](file:///C:/Users/zhanwang/AppData/Local/Temp/enhtmlclip/EN05b67f4a.png)

![img](file:///C:/Users/zhanwang/AppData/Local/Temp/enhtmlclip/EN05b67f5a.png)