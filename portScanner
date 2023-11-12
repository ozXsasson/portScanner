from socket import *

def conScan(tgtHost, tgtPort):
    try:
        conn = socket(AF_INET, SOCK_STREAM)
        conn.connect((tgtHost, tgtPort))
        print('[+]%d/tcp open'% tgtPort)
        conn.close()
    except:
        print('[-]%d/tcp closed'% tgtPort)

def portScan(tgtHost, tgtPorts):
    try:
        tgtIP = gethostbyname(tgtHost)
    except:
        print('[-] Cannot resolve %s'% tgtHost)
        return
    try:
        tgtName = gethostbyaddr(tgtIP)
        print('\n[+] Scan result of: %s' % tgtName[0])
    except:
        print('\n[+] Scan result of: %s' % tgtIP)

    setdefaulttimeout(1)
    for tgtPort in tgtPorts:
        print('Scanning Port: %d'% tgtPort)
        conScan(tgtHost, int(tgtPort))

if __name__ == '__main__':
    try:
        usrInput = input("[+] IP/Hostname of the site: ")
        portScan(usrInput, [22, 80])
    except:
        print("[-] Invalid Address")
