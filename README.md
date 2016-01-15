# Virus-Total-Public-API-Client-in-Java
VirusTotal's Public API lets you upload and scan files, submit and scan URLs, access finished scan reports and make automatic comments on URLs and samples without the need of using the HTML website interface.
## Sending and scanning files
### EXAMPLE 1
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
