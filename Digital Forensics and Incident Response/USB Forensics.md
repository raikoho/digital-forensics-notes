The first location we will discuss is the USBSTOR key which only holds information about external storage media/drives like USB, hard drive, etc.

**Registry Key:** HKLM\SYSTEM\CurrentControlSet\Enum\USBSTOR

USBSTOR is one of the first pieces of evidence in common forensics analysis including USB devices in the incidents. We can get information regarding the USB like its model and version name, the Windows-assigned serial number, the last connected timestamp, etc. These elements are crucial and can significantly contribute to determining the root cause of incidents, shedding light on the potential role of the USB, if any, in the occurrence.

![[Pasted image 20250219194251.png]]

- In the data section, we can see the timestamp in UTC.
- In the “0066” key we can find the timestamp when the USB was disconnected from the system.

---

**Registry Key:** HKLM\SYSTEM\CurrentControlSet\Enum\USB

This key contains information about all the devices connected through USB ports (For example keyboards, adapters, etc.)

![[Pasted image 20250219194407.png]]

---

# USB Event Logs

We will discuss these event logs:

- 1. Partition
- 2. Kernel-PnP
- 3. NTFS

## Partition

Now scroll to the partition log source from the above-mentioned log sources.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_2.png)

We are interested in event ID 1006:

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_3.png)

If we go to the details tab of the event corresponding to the timestamp identified in the registry artifacts we can see detailed information about the connected USB. Furthermore, the timestamp of this event aligns with the time of the USB connection, further affirming the timestamp is 08:05:07 AM on October 23, 2023.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_4.png)

We can see all the detailed information such as the Disk size of the USB in bytes, the serial number, the manufacturer, and the model.
## Kernel-PnP

Go to the relevant log source.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_5.png)

We are interested in Event IDs 400 and 410:

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_6.png)

Let's look closer into the event id 400:

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_7.png)

This event is logged when an external device like a USB is configured(backend term for connected) on the system.

We can see that the Device name is the same as we found in our USBSTOR key. Another artifact that aligns with our registry findings is the Class Guid. If you compare, you'll notice it matches the Guid present in the registry.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_8.png)

The timestamp of the event is exactly the same as the previous event log we discussed, as well as the registry.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_9.png)

This further provides evidence of when and which USB was connected to the system, and the metadata related to the USB device.

In the next lesson, we are gonna talk about the Directory paths inside the USB device. These can be used to understand for what purpose it was used and what kind of data contains.
## NTFS

Open the NTFS operational event log and filter for event ID 142. Then look for this event at the time when the USB was connected to the system, a time previously identified from the registry artifacts and the event logs we previously examined.

The NTFS event log is useful for us as it allows us to identify the Disk drive letter that was given to the USB. This helps in further investigation; if we encounter file paths starting with the disk letter assigned to the USB drive, we can get the context and understand that these files belong to that specific USB device.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_10.png)

We accessed the event with ID 142, occurring at the time of the USB connection, as previously identified.

Looking at the general tab of this event, we can note the volume name: "E:". This indicates that the "E:" disk letter was assigned to this specific USB device, and any file paths beginning with "E:" are associated with this device.

![](https://letsdefend-images.s3.us-east-2.amazonaws.com/Courses/USB+Forensics/3.USB+Event+Logs/image3_11.png)

This will help us in the next lessons as we will be dealing with file and folder paths.

In this part of the course, USB-related Event IDs are mentioned. In the next part of the course " **Folder Access Analysis via Shellbags** " will be explained.

----
# Automated USB Parsers Tools

## USB Detective

This tool automatically parses all the information and presents it in an organized way for analysis. All we have to do is provide the artifacts(Like the registry hives etc.) to the tool and it parses and presents all the information.

You can download the community edition of the tool from here:

**USB Detective** : [https://usbdetective.com/community-download/](https://usbdetective.com/community-download/)

