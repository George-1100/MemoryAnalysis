# MalwareAnalysis ina a wannacry ransomware infected system's image dump analyze by a volatility

# Description
  * Volatility is a Memory Analysis framework
  * Using FTK imager to dump a ram image
  * task is to analyze the wanacry infected system's dump image by Volatility

# Steps to reproduce
1. ![image](https://github.com/George-1100/MemoryAnalysis/assets/76154087/2d133050-0426-41dd-ae1a-44a2dbde104f)

   This command will show basic information about the OS image
 
2. ![image](https://github.com/George-1100/MemoryAnalysis/assets/76154087/f1f136dc-21e1-4029-8767-de13ba3f7298)

   This command will list the all process running on the sytem while taking dump image

3.  What is the name of the suspicious process?
    @WanaDecryptor

 4. What is the parent process ID for the suspicious process
    2732
    
 5. What is the initial malicious executable that created this process?
    or4qtckT.exe

    ![MF1](https://github.com/George-1100/MemoryAnalysis/assets/76154087/27985b3e-8528-4f30-ada0-7476a2a5bce3)
    
6. If you drill down on the suspicious PID (vol.py -f infected.vmem windows.psscan | grep --pid 2732, find the process used to delete files
   taskdll.exe
   
   ![image](https://github.com/George-1100/MemoryAnalysis/assets/76154087/f6e7624c-83cd-4879-b83f-ae6c9b6a3e36)

7. Find the path where the malicious file was first executed
   C:\Users\hacker\Desktop\or4qtckT.exe"

   ![image](https://github.com/George-1100/MemoryAnalysis/assets/76154087/3bd4160d-d82d-4818-8605-d2ea2e4bca04)


 9. Can you identify what ransomware it is?
    wannacry

  10. What is the filename for the file with the ransomware public key that was used to encrypt the private key? (.eky extension)
      00000000.eky
     python3 vol.py -f /home/george/Desktop/infected.vmem windows.handles --pid 2732
     Windows.handles used to find keys, files
      
   ![image](https://github.com/George-1100/MemoryAnalysis/assets/76154087/2d86c047-b4f1-447c-851a-f55e22e88fea)
  
