# Microsoft Sentinel Detection Rules
このリポジトリでは、Microsoft Sentinel向けに作成したKusto Query Language (KQL)の検知クエリを公開しています。  
本リポジトリは、Detection Engineeringのトレーニングおよびポートフォリオとして作成しています。  
検知ルールは、実際の攻撃手法を想定した設計を行っています。  

# 目的
本リポジトリでは以下のスキルを示すことを目的としています。  
・ Microsoft SentinelにおけるKQLを用いた検知クエリ設計  
・ MITRE ATT&CK を基にした検知設計  
・ 誤検知、検知漏れを考慮した検知クエリ作成  

# 検知対象
現在実装している検知クエリ  
①Credential Access：Password Spray Attack（T1110）  
②Credential Access：Low and Slow Password Spray（T1110）  
③Privilege Escalation：Account Manipulation（T1098）  
④Execution：Suspicious PowerShell（T1059.001）  
⑤Persistence：New Service（T1050）  
⑥Execution：・LOLBins certutil download（T1218）  

今後は以下の攻撃手法に対する検知を追加予定です。   
・Persistence：Scheduled Task  
・Defense Evansion：Log Delete  
・Lateral Movement：RDP、SMB  
・Credential Access：Brute Force SSH  
・Initial Access：Impossible Travel  
・Privilege Escalation：sudo、Kerberoasting  
・Discovery：Account Discovery  
・Collection：Email Collection  
・Exfiltation：Over Alternative Protocol  
・Impact：Data Encrypted  
・C2：DNS
など  

# リポジトリ構成
```
sentinel-detection-rules
README.md
detections/
    credential_access/
        password_spray.kql
        low_and_slow_password_spray.kql
    Execution/
        Suspicious_PowerShell_details.kql
        Suspicious_PowerShell_summary.kql
    Persistence/
        New_Service
    privilege escalation/
        Account _Manipulation.kql
```

# 検知クエリの構成
各検知クエリでは、以下の情報を整理しています。  
・クエリ (KQL)  
・検知内容の概要  
・検知の目的  
・誤検知パターンと対策  
・検知漏れパターンと対策  
・MITRE ATT&CKマッピング  
・ログソース  

# 使用ログ
主に以下の Microsoft Sentinel テーブルを使用しています。  
・SigninLogs  
・SecurityEvent  
・Event  
・AuditLogs  
・DeviceProcessEvents   
・DeviceEvents  
・DeviceFileEvents  
・OfficeActivity  
・CommonSecurityLog
・AzureNetworkAnalytics  
・DnsEvents  
・CommonSecurityLog  
・Syslog  
など（検知クエリの追加に合わせて拡充予定）
