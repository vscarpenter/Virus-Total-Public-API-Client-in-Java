# Virus-Total-Public-API-Client-in-Java
VirusTotal, a subsidiary of Google, is a free online service that analyzes files and URLs enabling the identification of viruses, worms, trojans and other kinds of malicious content detected by antivirus engines and website scanners. At the same time, it may be used as a means to detect false positives, i.e. innocuous resources detected as malicious by one or more scanners.
### Sending and scanning files
#### Example 1
#####
package me.vighnesh.api.virustotal.examples;

import java.io.File;
import java.io.IOException;
import me.vighnesh.api.virustotal.VirusTotalAPI;
import me.vighnesh.api.virustotal.dao.FileScanMetaData;

/**
 *
 * @author BVR vigneshb1210@gmail.com
 */
public class FileScanner {

    public static void main(String[] args) throws IOException {
        File file = new File("FILE YOU WANT TO SCAN");
        VirusTotalAPI virusTotal = VirusTotalAPI.configure("YOUR API KEY");
        FileScanMetaData scanFile = virusTotal.scanFile(file);
        System.out.println("---SCAN META DATA---");
        System.out.println("");
        System.out.println("MD5 : " + scanFile.getMD5());
        System.out.println("SH-1 : " + scanFile.getSHA1());
        System.out.println("SHA-256 : " + scanFile.getSHA256());
        System.out.println("Permalink : " + scanFile.getPermalink());
        System.out.println("Resource : " + scanFile.getResource());
        System.out.println("Scan Id : " + scanFile.getScanId());
        System.out.println("Response Code : " + scanFile.getResponseCode());
        System.out.println("Verbose Message : " + scanFile.getVerboseMessage());
    }
}