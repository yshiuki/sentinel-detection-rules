# Microsoft Sentinel Detection Rules
このリポジトリでは、Microsoft Sentinel向けに作成したKusto Query Language (KQL)の検知クエリを公開しています。
本リポジトリは、Detection Engineering のトレーニングおよびポートフォリオとして作成しています。
検知ルールは、実際の攻撃手法を想定し、SOC運用での利用を意識した設計を行っています。

# 目的
本リポジトリでは以下のスキルを示すことを目的としています。
・ Microsoft Sentinel におけるログ分析
・ KQL を用いた検知ロジック設計
・ MITRE ATT&CK を基にした検知設計
・ 誤検知を考慮した検知ロジック作成
・SOCにおけるインシデント調査を意識した検知ルール設計

# 検知対象
現在実装している検知ルール
①Credential Access：Password Spray Attack（T1110）
②Credential Access：Low and Slow Password Spray（T1110）

今後は以下の攻撃手法に対する検知を追加予定です。
・Privilege Escalation
・Lateral Movement
・Persistence
・Suspicious PowerShell Execution
・Privileged Account Abuse

# リポジトリ構成
```
sentinel-detection-rules
README.md
detections/
    credential_access/
        password_spray.md
        low_and_slow_password_spray.md
---
※detections フォルダには、SIEM の検知ルールとして利用することを想定した KQL クエリを配置しています。


# 検知ルールの構成
各検知ルールでは、以下の情報を整理しています。
・Description（検知内容の説明）
・MITRE ATT&CK Mapping
・Log Source
・Detection Logic (KQL)
・False Positive
・Investigation Steps
これらは SOC におけるインシデント対応プロセスを意識した構成となっています。

# 使用ログ
主に以下の Microsoft Sentinel テーブルを想定しています。
・SigninLogs
・SecurityEvent
・AuditLogs
・DeviceProcessEvents

# Detection Engineering アプローチ
本リポジトリでは以下の手順で検知ロジックを作成しています。
1. MITRE ATT&CK を基に攻撃手法を特定
2. 攻撃者の行動をログ上で分析
3. KQL を用いた検知ロジックを設計
4. 誤検知の可能性を評価
5. SOCでの調査手順を整理

# 今後の予定
以下の検知ルールを追加予定です。
・Privileged Group Modification
・Suspicious PowerShell
・Service Creation (EventID 7045)
・Lateral Movement (RDP / SMB)
・Impossible Travel
