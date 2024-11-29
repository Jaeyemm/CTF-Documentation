# ***SOC  FUNDAMENTALS***

## **SOC Roles:**

- **SOC Analyst (Level 1)**: Anything detected by the security solution would pass through these analysts first. These are the first responders to any detection. SOC Level 1 Analysts perform basic alert triage to determine if a specific detection is harmful. They also report these detections through proper channels.
- **SOC Analyst (Level 2)**: While Level 1 does the first-level analysis, some detections may require deeper investigation. Level 2 Analysts help them dive deeper into the investigations and correlate the data from multiple data sources to perform a proper analysis.
- **SOC Analyst (Level 3)**: Level 3 Analysts are experienced professionals who proactively look for any threat indicators and support in the incident response activities. The critical severity detection reported by Level 1 and Level 2 Analysts are often security incidents that need detailed responses, including containment, eradication, and recovery. This is where Level 3 analysts’ experience comes in handy.
- **Security Engineer**: All analysts work on security solutions. These solutions need deployment and configuration. Security Engineers deploy and configure these security solutions to ensure their smooth operation.
- **Detection Engineer**: Security rules are the logic built behind security solutions to detect harmful activities. Level 2 and 3 Analysts often create these rules, while the SOC team can sometimes also utilize the detection engineer role independently for this responsibility.
- **SOC Manager**: The SOC Manager manages the processes the SOC team follows and provides support. The SOC Manager also remains in contact with the organization’s CISO (Chief Information Security Officer) to provide him with updates on the SOC team’s current security posture and efforts.

## 5 Ws

**What?**	A malicious file was detected on one of the hosts inside the organization’s network.

**When?**	The file was detected at 13:20 on June 5, 2024.

**Where?**	The file was detected in the directory of the host: "GEORGE PC".

**Who?**	The file was detected for the user George.

**Why?**	After the investigation, it was found that the file was downloaded from a pirated software-selling website. The investigation with the user revealed that they downloaded the file as they wanted to use a software for free.

SIEM Dectection popular tool used in almost every SOC environment. This tool collects logs from various network devices, referred to as log sources. Detection rules are configured in the SIEM solution, which contains logic to identify suspicious activity.

## ***Digital Forensics***

# **Digital Forensics Methodology**

- Collection: The first phase of digital forensics is data collection. Identifying all the devices from which the data can be collected is essential. Usually, an investigator can find personal computers, laptops, digital cameras, USBs, etc., on the crime scene. It is also necessary to ensure the original data is not tampered with while collecting the evidence and to maintain a proper document containing the collected items’ details. We will also be discussing the evidence-acquisition procedures in the upcoming tasks.
- Examination: The collected data may overwhelm investigators due to its size. This data usually needs to be filtered, and the data of interest needs to be extracted. For example, as an investigator, you collected all the media files from a digital camera on the crime scene. You may only require some of the media as you are concerned with the media recorded on a specific date and time. So, in the examination phase, you would filter the media files of the required time and move them to the next phase. Similarly, you may only need the data of a specific user from a system containing numerous user accounts. The examination phase helps you filter this particular data for analysis.
- Analysis: This is a critical phase. The investigators now have to analyze the data by correlating it with multiple pieces of evidence to draw conclusions. The analysis depends upon the case scenario and available data. The analysis aims to extract the activities relevant to the case chronologically.
- Reporting: In the last phase of digital forensics, a detailed report is prepared. This report contains the investigation’s methodology and detailed findings from the collected evidence. It may also contain recommendations. This report is presented to law enforcement and executive management. It is important to include executive summaries as part of the report, considering the level of understanding of all the receiving parties.

**Chain of Custody**

- Description of the evidence (name, type).
-Name of individuals who collected the evidence.
- Date and time of evidence collection.
- Storage location of each piece of evidence.
- Access times and the individual record who accessed the evidence.

**Use of Write Blockers**

Write blockers are an essential part of the digital forensics team’s toolbox. Suppose you are collecting evidence from a suspect’s hard drive and attaching the hard drive to the forensic workstation. While the collection occurs, some background tasks in the forensic workstation may alter the timestamps of the files on the hard drive. This can cause hindrances during the analysis, ultimately producing incorrect results. Suppose the data was collected from the hard drive using a write blocker instead in the same scenario. This time, the suspect’s hard drive would remain in its original state as the write blocker can block any evidence alteration actions.

## **Data Collection Phase**

forensic images of the Windows operating system are taken. These forensic images are bit-by-bit copies of the whole operating system. Two different categories of forensic images are taken from a Windows operating system.

Disk image: The disk image contains all the data present on the storage device of the system (HDD, SSD, etc.). This data is non-volatile, meaning that the disk data would survive even after a restart of the operating system. For example, all the files like media, documents, internet browsing history, and more.

Memory image: The memory image contains the data inside the operating system’s RAM. This memory is volatile, meaning the data will get lost after the system is powered off or restarted. For example, to capture open files, running processes, current network connections, etc., the memory image should be prioritized and taken first from the suspect’s operating system; otherwise, any restart or shutdown of the system would result in all the volatile data getting deleted. While carrying out digital forensics on a Windows operating system, disk and memory images are very important to collect.

Let’s discuss some popular tools used for disk and memory image acquisition and analysis of the Windows operating system.

## **Disk and memory image acquisition and analysis of the Windows operating system**

**FTK Imager**: FTK Imager is a widely used tool for taking disk images of Windows operating systems. It offers a user-friendly graphical interface for creating the image in various formats. This tool can also analyze the contents of a disk image. It can be used for both acquisition and analysis purposes.

**Autopsy**: Autopsy is a popular open-source digital forensics platform. An investigator can import an acquired disk image into this tool, and the tool will conduct an extensive analysis of the image. It offers various features during image analysis, including keyword search, deleted file recovery, file metadata, extension mismatch detection, and many more.

**DumpIt**: DumpIt offers the utility of taking a memory image from a Windows operating system. This tool creates memory images using a command-line interface and a few commands. The memory image can also be taken in different formats.

**Volatility**: Volatility is a powerful open-source tool for analyzing memory images. It offers some extremely useful plugins. Each artifact can be analyzed using a specific plugin. This tool supports various operating systems, including Windows, Linux, macOS, and Android.

