---
title: セキュリティ識別子のグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: 83326c13de7585806ab841f728f587f1131b5e8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325990"
---
# <a name="security-identifier-global-functions"></a>セキュリティ識別子のグローバル関数

これらの関数は、一般的な既知の SID オブジェクトを返します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID を返します。|
|[Sids::Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID を返します。|
|[Sids::AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID を返します。|
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID を返します。|
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID を返します。|
|[Sids::Batch](#batch)|SECURITY_BATCH_RID SID を返します。|
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID を返します。|
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID を返します。|
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID を返します。|
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID を返します。|
|[Sids::Dialup](#dialup)|SECURITY_DIALUP_RID SID を返します。|
|[Sids::Guests](#guests)|DOMAIN_ALIAS_RID_GUESTS SID を返します。|
|[Sids::Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID を返します。|
|[Sids::Local](#local)|SECURITY_LOCAL_RID SID を返します。|
|[Sids::Network](#network)|SECURITY_NETWORK_RID SID を返します。|
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID を返します。|
|[Sids::Null](#null)|SECURITY_NULL_RID SID を返します。|
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID を返します。|
|[Sids::PowerUsers](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID を返します。|
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID を返します。|
|[Sids::Proxy](#proxy)|SECURITY_PROXY_RID SID を返します。|
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID を返します。|
|[Sids::Replicator](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID を返します。|
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID を返します。|
|[Sids::Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID を返します。|
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID を返します。|
|[Sids::Service](#service)|SECURITY_SERVICE_RID SID を返します。|
|[Sids::System](#system)|SECURITY_LOCAL_SYSTEM_RID SID を返します。|
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID を返します。|
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID を返します。|
|[Sids::Users](#users)|DOMAIN_ALIAS_RID_USERS SID を返します。|
|[シッズ::世界](#world)|SECURITY_WORLD_RID SID を返します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="sidsaccountops"></a><a name="accountops"></a>シド::アカウントオプス

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID を返します。

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a>シド::管理者

DOMAIN_ALIAS_RID_ADMINS SID を返します。

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a>シズ::匿名ログオン

SECURITY_ANONYMOUS_LOGON_RID SID を返します。

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a>シズ::認証されたユーザー

SECURITY_AUTHENTICATED_USER_RID SID を返します。

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a>シド::バックアップオプス

DOMAIN_ALIAS_RID_BACKUP_OPS SID を返します。

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a>シド::バッチ

SECURITY_BATCH_RID SID を返します。

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a>シッズ::クリエイターグループ

SECURITY_CREATOR_GROUP_RID SID を返します。

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a>シッズ::クリエイターグループサーバー

SECURITY_CREATOR_GROUP_SERVER_RID SID を返します。

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a>シズ::クリエイターオーナー

SECURITY_CREATOR_OWNER_RID SID を返します。

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a>シズ::クリエイターオーナーサーバー

SECURITY_CREATOR_OWNER_SERVER_RID SID を返します。

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a>シズ::D

SECURITY_DIALUP_RID SID を返します。

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a>シッズ::ゲスト

DOMAIN_ALIAS_RID_GUESTS SID を返します。

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a>シッズ::インタラクティブ

SECURITY_INTERACTIVE_RID SID を返します。

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a>シッズ::ローカル

SECURITY_LOCAL_RID SID を返します。

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a>シド::ネットワーク

SECURITY_NETWORK_RID SID を返します。

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a>シズ::ネットワークサービス

SECURITY_NETWORK_SERVICE_RID SID を返します。

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>解説

ネットワーク サービスを使用して、NT オーソリティ\ネットワーク サービス ユーザーが CPerfMon セキュリティ オブジェクトを読み取るようにします。 ネットワーク サービスは、WINDOWS XP ホーム エディション、Windows XP プロフェッショナル、Windows Server 2003 およびより大きなオペレーティング システム上のネットワーク サービス アカウントで DLL がログインできるようにする ATLServer コードにセキュリティ属性を追加します。

カスタム ログ カウンタが PERFmon MMC の ATLServer CPerfMon クラスで作成されると、リアルタイム ビューでは正しく表示されますが、ログ ファイルを表示するときにカウンタが表示されないことがあります。 CPerfMon カスタム パフォーマンス カウンタには、Windows XP ホーム エディション、Windows XP プロフェッショナル、Windows Server 2003 (またはそれ以上) のオペレーティング システムの "パフォーマンス ログと警告" サービス (smlogsvc.exe) で実行するために必要なアクセス許可がありません。 このサービスは、"NT オーソリティ\ネットワーク サービス" アカウントで実行されます。

## <a name="sidsnull"></a><a name="null"></a>シッズ::ヌル

SECURITY_NULL_RID SID を返します。

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a>シド::PreW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID を返します。

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a>シッズ::Pワーユーザー

DOMAIN_ALIAS_RID_POWER_USERS SID を返します。

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a>シッズ::Pリントプス

DOMAIN_ALIAS_RID_PRINT_OPS SID を返します。

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a>シド::Pロキシー

SECURITY_PROXY_RID SID を返します。

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a>シド::ラスサーバー

DOMAIN_ALIAS_RID_RAS_SERVERS SID を返します。

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a>シズ::レプリケータ

DOMAIN_ALIAS_RID_REPLICATOR SID を返します。

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a>シッズ::制限付きコード

SECURITY_RESTRICTED_CODE_RID SID を返します。

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a>シッズ::自己

SECURITY_PRINCIPAL_SELF_RID SID を返します。

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a>シズ::サーバーログオン

SECURITY_SERVER_LOGON_RID SID を返します。

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a>シッズ::サービス

SECURITY_SERVICE_RID SID を返します。

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a>シッズ::システム

SECURITY_LOCAL_SYSTEM_RID SID を返します。

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a>シド::システムオプス

DOMAIN_ALIAS_RID_SYSTEM_OPS SID を返します。

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a>シッズ::ターミナルサーバー

SECURITY_TERMINAL_SERVER_RID SID を返します。

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a>シド::ユーザー

DOMAIN_ALIAS_RID_USERS SID を返します。

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a>シッズ::世界

SECURITY_WORLD_RID SID を返します。

```
CSid World() throw(...);
```

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
