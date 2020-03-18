---
title: CAccessToken クラス
ms.date: 07/02/2019
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: 33fbaae5dafaccdf7f7e6880eaa42dd68352e840
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423520"
---
# <a name="caccesstoken-class"></a>CAccessToken クラス

このクラスは、アクセストークンのラッパーです。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAccessToken
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CAccessToken:: ~ CAccessToken](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CAccessToken:: Attach](#attach)|このメソッドを呼び出して、指定されたアクセストークンハンドルの所有権を取得します。|
|[CAccessToken:: CheckTokenMembership](#checktokenmembership)|指定した SID が `CAccessToken` オブジェクトで有効になっているかどうかを確認するには、このメソッドを呼び出します。|
|[CAccessToken:: CreateImpersonationToken](#createimpersonationtoken)|新しい権限借用アクセストークンを作成するには、このメソッドを呼び出します。|
|[CAccessToken:: CreatePrimaryToken](#createprimarytoken)|新しいプライマリトークンを作成するには、このメソッドを呼び出します。|
|[CAccessToken:: Createprocessasuser が](#createprocessasuser)|このメソッドを呼び出して、`CAccessToken` オブジェクトによって表されるユーザーのセキュリティコンテキストで実行される新しいプロセスを作成します。|
|[CAccessToken:: CreateRestrictedToken](#createrestrictedtoken)|新しい制限付き `CAccessToken` オブジェクトを作成するには、このメソッドを呼び出します。|
|[CAccessToken::D etach](#detach)|アクセストークンの所有権を取り消すには、このメソッドを呼び出します。|
|[CAccessToken::D isablePrivilege](#disableprivilege)|`CAccessToken` オブジェクトの特権を無効にするには、このメソッドを呼び出します。|
|[CAccessToken::D isablePrivileges](#disableprivileges)|このメソッドを呼び出して、`CAccessToken` オブジェクト内の1つ以上の特権を無効にします。|
|[CAccessToken:: EnablePrivilege](#enableprivilege)|`CAccessToken` オブジェクトの特権を有効にするには、このメソッドを呼び出します。|
|[CAccessToken:: EnablePrivileges](#enableprivileges)|`CAccessToken` オブジェクトで1つ以上の特権を有効にするには、このメソッドを呼び出します。|
|[CAccessToken:: GetDefaultDacl](#getdefaultdacl)|`CAccessToken` オブジェクトの既定の DACL を返すには、このメソッドを呼び出します。|
|[CAccessToken:: GetEffectiveToken](#geteffectivetoken)|現在のスレッドで有効になっているアクセストークンと等しい `CAccessToken` オブジェクトを取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetGroups](#getgroups)|`CAccessToken` オブジェクトのトークングループを返すには、このメソッドを呼び出します。|
|[CAccessToken:: GetHandle](#gethandle)|アクセストークンへのハンドルを取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetImpersonationLevel](#getimpersonationlevel)|アクセストークンから偽装レベルを取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetLogonSessionId](#getlogonsessionid)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているログオンセッション ID を取得します。|
|[CAccessToken:: GetLogonSid](#getlogonsid)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているログオン SID を取得します。|
|[CAccessToken:: GetOwner](#getowner)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられている所有者を取得します。|
|[CAccessToken:: GetPrimaryGroup](#getprimarygroup)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているプライマリグループを取得します。|
|[CAccessToken:: GetPrivileges](#getprivileges)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられている特権を取得します。|
|[CAccessToken:: GetProcessToken](#getprocesstoken)|指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。|
|[CAccessToken:: GetProfile](#getprofile)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを指すハンドルを取得します。|
|[CAccessToken:: GetSource](#getsource)|`CAccessToken` オブジェクトのソースを取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetStatistics](#getstatistics)|`CAccessToken` オブジェクトに関連付けられている情報を取得するには、このメソッドを呼び出します。|
|[CAccessToken:: Getターミナルサービスのセッション id](#getterminalservicessessionid)|`CAccessToken` オブジェクトに関連付けられているターミナルサービスセッション ID を取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetThreadToken](#getthreadtoken)|このメソッドを呼び出して、指定されたスレッドからのトークンを使用して `CAccessToken` を初期化します。|
|[CAccessToken:: GetTokenId](#gettokenid)|`CAccessToken` オブジェクトに関連付けられているトークン ID を取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetType](#gettype)|`CAccessToken` オブジェクトのトークン型を取得するには、このメソッドを呼び出します。|
|[CAccessToken:: GetUser](#getuser)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザーを識別します。|
|[CAccessToken:: HKeyCurrentUser](#hkeycurrentuser)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを指すハンドルを取得します。|
|[CAccessToken:: Impersonate](#impersonate)|偽装 `CAccessToken` をスレッドに割り当てるには、このメソッドを呼び出します。|
|[CAccessToken:: ImpersonateLoggedOnUser](#impersonateloggedonuser)|呼び出し元のスレッドが、ログオンしているユーザーのセキュリティコンテキストを偽装できるようにするには、このメソッドを呼び出します。|
|[CAccessToken:: IsTokenRestricted](#istokenrestricted)|`CAccessToken` オブジェクトに制限付き Sid の一覧が含まれているかどうかをテストするには、このメソッドを呼び出します。|
|[CAccessToken:: Processmodel.loaduserprofile](#loaduserprofile)|このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを読み込みます。|
|[CAccessToken:: LogonUser](#logonuser)|指定した資格情報に関連付けられているユーザーのログオンセッションを作成するには、このメソッドを呼び出します。|
|[CAccessToken:: OpenCOMClientToken](#opencomclienttoken)|クライアントからの呼び出しを処理する COM サーバー内からこのメソッドを呼び出して、COM クライアントからアクセストークンを使用して `CAccessToken` を初期化します。|
|[CAccessToken:: OpenNamedPipeClientToken](#opennamedpipeclienttoken)|名前付きパイプに対する要求を取得するサーバー内からこのメソッドを呼び出して、クライアントからアクセストークンを使用して `CAccessToken` を初期化します。|
|[CAccessToken:: OpenRPCClientToken](#openrpcclienttoken)|RPC クライアントからの呼び出しを処理するサーバー内からこのメソッドを呼び出して、クライアントからアクセストークンを使用して `CAccessToken` を初期化します。|
|[CAccessToken:: OpenThreadToken](#openthreadtoken)|このメソッドを呼び出して、偽装レベルを設定し、指定されたスレッドのトークンを使用して `CAccessToken` を初期化します。|
|[CAccessToken::P rivilegeCheck](#privilegecheck)|このメソッドを呼び出して、`CAccessToken` オブジェクトで、指定した権限のセットが有効になっているかどうかを確認します。|
|[CAccessToken:: Revert](#revert)|偽装トークンを使用しているスレッドを停止するには、このメソッドを呼び出します。|
|[CAccessToken:: SetDefaultDacl](#setdefaultdacl)|`CAccessToken` オブジェクトの既定の DACL を設定するには、このメソッドを呼び出します。|
|[CAccessToken:: SetOwner](#setowner)|`CAccessToken` オブジェクトの所有者を設定するには、このメソッドを呼び出します。|
|[CAccessToken:: SetPrimaryGroup](#setprimarygroup)|`CAccessToken` オブジェクトのプライマリグループを設定するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

[アクセストークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティコンテキストを記述するオブジェクトで、Windows システムにログオンした各ユーザーに割り当てられます。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity .h

##  <a name="attach"></a>CAccessToken:: Attach

このメソッドを呼び出して、指定されたアクセストークンハンドルの所有権を取得します。

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>パラメーター

*hToken*<br/>
アクセストークンへのハンドル。

### <a name="remarks"></a>解説

デバッグビルドでは、`CAccessToken` オブジェクトに既にアクセストークンの所有権がある場合、アサーションエラーが発生します。

##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken

デストラクターです。

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

##  <a name="checktokenmembership"></a>CAccessToken:: CheckTokenMembership

指定した SID が `CAccessToken` オブジェクトで有効になっているかどうかを確認するには、このメソッドを呼び出します。

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへの参照。

*pbIsMember*<br/>
チェックの結果を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CheckTokenMembership` メソッドは、アクセストークンのユーザーとグループの sid に SID が存在するかどうかを確認します。 SID が存在し、SE_GROUP_ENABLED 属性を持っている場合、 *Pbismember*は TRUE に設定されます。それ以外の場合は、FALSE に設定されます。

デバッグビルドでは、 *Pbismember*が有効なポインターでない場合にアサーションエラーが発生します。

> [!NOTE]
>  `CAccessToken` オブジェクトは、プライマリトークンではなく、偽装トークンである必要があります。

##  <a name="createimpersonationtoken"></a>CAccessToken:: CreateImpersonationToken

偽装アクセストークンを作成するには、このメソッドを呼び出します。

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pImp*<br/>
新しい `CAccessToken` オブジェクトへのポインター。

*sil*<br/>
新しいトークンの偽装レベルを提供する[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)列挙型を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateImpersonationToken` は、 [DuplicateToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken)を呼び出して新しい権限借用トークンを作成します。

##  <a name="createprimarytoken"></a>CAccessToken:: CreatePrimaryToken

新しいプライマリトークンを作成するには、このメソッドを呼び出します。

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pPri*<br/>
新しい `CAccessToken` オブジェクトへのポインター。

*dwDesiredAccess*<br/>
新しいトークンに要求されたアクセス権を指定します。 既定の MAXIMUM_ALLOWED は、呼び出し元に対して有効なすべてのアクセス権を要求します。 アクセス権の詳細については、「アクセス権[とアクセスマスク](/windows/win32/SecAuthZ/access-rights-and-access-masks)」を参照してください。

*pTokenAttributes*<br/>
新しいトークンのセキュリティ記述子を指定し、子プロセスがトークンを継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *Ptokenattributes*が NULL の場合、トークンは既定のセキュリティ記述子を取得し、ハンドルを継承することはできません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreatePrimaryToken` は、 [DuplicateTokenEx](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex)を呼び出して新しいプライマリトークンを作成します。

##  <a name="createprocessasuser"></a>CAccessToken:: Createprocessasuser が

このメソッドを呼び出して、`CAccessToken` オブジェクトによって表されるユーザーのセキュリティコンテキストで実行される新しいプロセスを作成します。

```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*pApplicationName*<br/>
実行するモジュールを指定する null で終わる文字列へのポインター。 このパラメーターを NULL にすることはできません。

*pCommandLine*<br/>
実行するコマンドラインを指定する null で終わる文字列へのポインター。

*pProcessInformation*<br/>
新しいプロセスに関する識別情報を受け取る[PROCESS_INFORMATION 構造体](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information)へのポインター。

*pStartupInfo*<br/>
新しいプロセスのメインウィンドウをどのように表示するかを指定する[Startupinfo](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow)構造体へのポインター。

*Dwのフラグ*<br/>
優先度クラスとプロセスの作成を制御する追加のフラグを指定します。 フラグの一覧については、「Win32 関数[createprocessasuser が](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw)」を参照してください。

*bLoadProfile*<br/>
TRUE の場合、ユーザーのプロファイルは[processmodel.loaduserprofile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)で読み込まれます。

*pProcessAttributes*<br/>
新しいプロセスのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *Pprocessattributes*が NULL の場合、プロセスは既定のセキュリティ記述子を取得し、ハンドルを継承することはできません。

*pThreadAttributes*<br/>
新しいスレッドのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *Pthreadattributes*が NULL の場合、スレッドは既定のセキュリティ記述子を取得し、ハンドルを継承することはできません。

*bInherit*<br/>
新しいプロセスが呼び出しプロセスからハンドルを継承するかどうかを示します。 TRUE の場合、呼び出し元のプロセスで、継承可能な各開いているハンドルが新しいプロセスによって継承されます。 継承されたハンドルには、元のハンドルと同じ値とアクセス特権があります。

*pCurrentDirectory*<br/>
新しいプロセスの現在のドライブとディレクトリを指定する、null で終わる文字列へのポインター。 文字列は、ドライブ文字を含む完全なパスである必要があります。 このパラメーターが NULL の場合、新しいプロセスは呼び出しプロセスと同じ現在のドライブとディレクトリを持ちます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateProcessAsUser` は、`CreateProcessAsUser` Win32 関数を使用して、`CAccessToken` オブジェクトによって表されるユーザーのセキュリティコンテキストで実行される新しいプロセスを作成します。 必要なパラメーターの詳細については、 [createprocessasuser が](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw)関数の説明を参照してください。

このメソッドを成功させるには、`CAccessToken` オブジェクトが割り当て Primarytoken (制限付きトークン) と IncreaseQuota 特権を保持している必要があります。

##  <a name="createrestrictedtoken"></a>CAccessToken:: CreateRestrictedToken

新しい制限付き `CAccessToken` オブジェクトを作成するには、このメソッドを呼び出します。

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pRestrictedToken*<br/>
新しい、制限付き `CAccessToken` オブジェクト。

*SidsToDisable*<br/>
拒否専用の Sid を指定する `CTokenGroups` オブジェクト。

*SidsToRestrict*<br/>
制限する Sid を指定する `CTokenGroups` オブジェクト。

*PrivilegesToDelete*<br/>
制限付きトークン内で削除する特権を指定する `CTokenPrivileges` オブジェクト。 既定では、空のオブジェクトが作成されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateRestrictedToken` は、 [CreateRestrictedToken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 関数を使用して、制限付きの新しい `CAccessToken` オブジェクトを作成します。

> [!IMPORTANT]
>  `CreateRestrictedToken`を使用する場合は、既存のトークンが有効であり (ユーザーが入力していない)、 *Sidstodisable*と*PrivilegesToDelete*の両方が有効である (ユーザーが入力していない) ことを確認します。 メソッドが FALSE を返す場合は、機能を拒否します。

##  <a name="detach"></a>CAccessToken::D etach

アクセストークンの所有権を取り消すには、このメソッドを呼び出します。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

デタッチされた `CAccessToken` へのハンドルを返します。

### <a name="remarks"></a>解説

このメソッドは、アクセストークンの `CAccessToken`の所有権を取り消します。

##  <a name="disableprivilege"></a>CAccessToken::D isablePrivilege

`CAccessToken` オブジェクトの特権を無効にするには、このメソッドを呼び出します。

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*<br/>
`CAccessToken` オブジェクトで無効にする特権を格納している文字列へのポインター。

*Pの状態*<br/>
特権の以前の状態を格納する `CTokenPrivileges` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="disableprivileges"></a>CAccessToken::D isablePrivileges

このメソッドを呼び出して、`CAccessToken` オブジェクト内の1つ以上の特権を無効にします。

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*rPrivileges*<br/>
`CAccessToken` オブジェクトで無効にする特権を格納している文字列の配列へのポインター。

*Pの状態*<br/>
特権の以前の状態を格納する `CTokenPrivileges` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="enableprivilege"></a>CAccessToken:: EnablePrivilege

`CAccessToken` オブジェクトの特権を有効にするには、このメソッドを呼び出します。

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*<br/>
`CAccessToken` オブジェクトで有効にする特権を格納している文字列へのポインター。

*Pの状態*<br/>
特権の以前の状態を格納する `CTokenPrivileges` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="enableprivileges"></a>CAccessToken:: EnablePrivileges

`CAccessToken` オブジェクトで1つ以上の特権を有効にするには、このメソッドを呼び出します。

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*rPrivileges*<br/>
`CAccessToken` オブジェクトで有効にする特権を格納している文字列の配列へのポインター。

*Pの状態*<br/>
特権の以前の状態を格納する `CTokenPrivileges` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getdefaultdacl"></a>CAccessToken:: GetDefaultDacl

`CAccessToken` オブジェクトの既定の DACL を返すには、このメソッドを呼び出します。

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pDacl*<br/>
`CAccessToken` オブジェクトの既定の DACL を受け取る[CDacl クラス](../../atl/reference/cdacl-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

既定の DACL が回復されている場合は TRUE、それ以外の場合は FALSE を返します。

##  <a name="geteffectivetoken"></a>CAccessToken:: GetEffectiveToken

現在のスレッドで有効になっているアクセストークンと等しい `CAccessToken` オブジェクトを取得するには、このメソッドを呼び出します。

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>パラメーター

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getgroups"></a>CAccessToken:: GetGroups

`CAccessToken` オブジェクトのトークングループを返すには、このメソッドを呼び出します。

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pGroups*<br/>
グループ情報を受け取る[Ctokengroups クラス](../../atl/reference/ctokengroups-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="gethandle"></a>CAccessToken:: GetHandle

アクセストークンへのハンドルを取得するには、このメソッドを呼び出します。

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>戻り値

`CAccessToken` オブジェクトのアクセストークンへのハンドルを返します。

##  <a name="getimpersonationlevel"></a>CAccessToken:: GetImpersonationLevel

アクセストークンから偽装レベルを取得するには、このメソッドを呼び出します。

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pImpersonationLevel*<br/>
偽装レベル情報を受け取る[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)列挙型へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getlogonsessionid"></a>CAccessToken:: GetLogonSessionId

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているログオンセッション ID を取得します。

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pluid*<br/>
ログオンセッション ID を受け取る[LUID](/windows/win32/api/winnt/ns-winnt-luid)へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *pluid*が無効な値の場合、アサーションエラーが発生します。

##  <a name="getlogonsid"></a>CAccessToken:: GetLogonSid

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているログオン SID を取得します。

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *pSid*が無効な値の場合、アサーションエラーが発生します。

##  <a name="getowner"></a>CAccessToken:: GetOwner

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられている所有者を取得します。

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このアクセストークンが有効になっている間に作成されたオブジェクトには、既定で所有者が設定されます。

##  <a name="getprimarygroup"></a>CAccessToken:: GetPrimaryGroup

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているプライマリグループを取得します。

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このアクセストークンが有効になっている間に作成されたオブジェクトには、グループが既定で設定されます。

##  <a name="getprivileges"></a>CAccessToken:: GetPrivileges

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられている特権を取得します。

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pPrivileges*<br/>
特権を受け取る[CTokenPrivileges クラス](../../atl/reference/ctokenprivileges-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getprocesstoken"></a>CAccessToken:: GetProcessToken

指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*hProcess*<br/>
アクセス トークンが開いているプロセスへのハンドル。 既定値の NULL が使用されている場合は、現在のプロセスが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32 関数を呼び出します。

##  <a name="getprofile"></a>CAccessToken:: GetProfile

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを指すハンドルを取得します。

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>戻り値

ユーザープロファイルを指すハンドルを返します。プロファイルが存在しない場合は NULL を返します。

##  <a name="getsource"></a>CAccessToken:: GetSource

`CAccessToken` オブジェクトのソースを取得するには、このメソッドを呼び出します。

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSource*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getstatistics"></a>CAccessToken:: GetStatistics

`CAccessToken` オブジェクトに関連付けられている情報を取得するには、このメソッドを呼び出します。

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pStatistics*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getterminalservicessessionid"></a>CAccessToken:: Getターミナルサービスのセッション id

`CAccessToken` オブジェクトに関連付けられているターミナルサービスセッション ID を取得するには、このメソッドを呼び出します。

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pdwSessionId*<br/>
ターミナルサービスのセッション ID。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="getthreadtoken"></a>CAccessToken:: GetThreadToken

このメソッドを呼び出して、指定されたスレッドからのトークンを使用して `CAccessToken` を初期化します。

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>パラメーター

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*hThread*<br/>
アクセストークンが開かれているスレッドへのハンドル。

*bOpenAsSelf*<br/>
`GetThreadToken` メソッドを呼び出しているスレッドのセキュリティコンテキスト、または呼び出し元のスレッドのプロセスのセキュリティコンテキストに対してアクセスチェックを実行するかどうかを示します。

このパラメーターが FALSE の場合は、呼び出し元のスレッドのセキュリティコンテキストを使用してアクセスチェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティコンテキストはクライアントプロセスのものである可能性があります。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="gettokenid"></a>CAccessToken:: GetTokenId

`CAccessToken` オブジェクトに関連付けられているトークン ID を取得するには、このメソッドを呼び出します。

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pluid*<br/>
トークン ID を受け取る[LUID](/windows/win32/api/winnt/ns-winnt-luid)へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="gettype"></a>CAccessToken:: GetType

`CAccessToken` オブジェクトのトークン型を取得するには、このメソッドを呼び出します。

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pType*<br/>
成功した場合は、トークンの型を受け取る[TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type)変数のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

TOKEN_TYPE 列挙型には、プライマリトークンと偽装トークンを区別する値が含まれています。

##  <a name="getuser"></a>CAccessToken:: GetUser

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザーを識別します。

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

##  <a name="hkeycurrentuser"></a>CAccessToken:: HKeyCurrentUser

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを指すハンドルを取得します。

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>戻り値

ユーザープロファイルを指すハンドルを返します。プロファイルが存在しない場合は NULL を返します。

##  <a name="impersonate"></a>CAccessToken:: Impersonate

偽装 `CAccessToken` をスレッドに割り当てるには、このメソッドを呼び出します。

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*hThread*<br/>
偽装トークンを割り当てるスレッドへのハンドル。 このハンドルは TOKEN_IMPERSONATE アクセス権で開かれている必要があります。 *Hthread*が NULL の場合、メソッドは偽装トークンを使用してスレッドを停止します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、`CAccessToken` にトークンへの有効なポインターがない場合、アサーションエラーが発生します。

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると、偽装されたアクセストークンを自動的に元に戻すことができます。

##  <a name="impersonateloggedonuser"></a>CAccessToken:: ImpersonateLoggedOnUser

呼び出し元のスレッドが、ログオンしているユーザーのセキュリティコンテキストを偽装できるようにするには、このメソッドを呼び出します。

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

> [!IMPORTANT]
>  何らかの理由で権限借用関数の呼び出しが失敗した場合、クライアントは偽装されず、クライアント要求は呼び出し元のプロセスのセキュリティコンテキストで行われます。 プロセスが高い特権を持つアカウントとして実行されている場合、または管理グループのメンバーとして実行されている場合、ユーザーは、許可されていないアクションを実行できる可能性があります。 したがって、この関数の戻り値は常に確認する必要があります。

##  <a name="istokenrestricted"></a>CAccessToken:: IsTokenRestricted

`CAccessToken` オブジェクトに制限付き Sid の一覧が含まれているかどうかをテストするには、このメソッドを呼び出します。

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに Sid 制限の一覧が含まれている場合は TRUE、制限する Sid がない場合、またはメソッドが失敗した場合は FALSE を返します。

##  <a name="loaduserprofile"></a>CAccessToken:: Processmodel.loaduserprofile

このメソッドを呼び出して、`CAccessToken` オブジェクトに関連付けられているユーザープロファイルを読み込みます。

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、`CAccessToken` に有効なトークンが含まれていない場合、またはユーザープロファイルが既に存在する場合、アサーションエラーが発生します。

##  <a name="logonuser"></a>CAccessToken:: LogonUser

指定した資格情報に関連付けられているユーザーのログオンセッションを作成するには、このメソッドを呼び出します。

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*pszUserName*<br/>
ユーザー名を指定する null で終わる文字列へのポインター。 これは、ログオン先のユーザーアカウントの名前です。

*pszDomain*<br/>
アカウントデータベースに*Pszusername*アカウントが含まれているドメインまたはサーバーの名前を指定する null で終わる文字列へのポインター。

*pszPassword*<br/>
*Pszusername*によって指定されたユーザーアカウントのクリアテキストパスワードを指定する、null で終わる文字列へのポインター。

*dwLogonType*<br/>
実行するログオン操作の種類を指定します。 詳細については、「 [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) 」を参照してください。

*dwLogonProvider*<br/>
ログオンプロバイダーを指定します。 詳細については、「 [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) 」を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

ログオンによって生成されるアクセストークンは、`CAccessToken`に関連付けられます。 このメソッドを成功させるには、`CAccessToken` オブジェクトは、信頼されたコンピューターベースの一部として所有者を識別する SE_TCB_NAME の特権を保持する必要があります。 必要な特権に関する詳細については、「 [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) 」を参照してください。

##  <a name="opencomclienttoken"></a>CAccessToken:: OpenCOMClientToken

クライアントからの呼び出しを処理する COM サーバー内からこのメソッドを呼び出して、COM クライアントからアクセストークンを使用して `CAccessToken` を初期化します。

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*bImpersonate*<br/>
TRUE の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の COM クライアントを偽装します。 FALSE の場合、アクセストークンは開かれますが、この呼び出しが完了してもスレッドは偽装トークンを持ちません。

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティコンテキスト、または呼び出し元のスレッドのプロセスのセキュリティコンテキストに対してアクセスチェックを実行するかどうかを示します。

このパラメーターが FALSE の場合は、呼び出し元のスレッドのセキュリティコンテキストを使用してアクセスチェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティコンテキストはクライアントプロセスのものである可能性があります。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると、 *BIMPERSONATE*フラグを TRUE に設定することによって作成された偽装アクセストークンを自動的に元に戻すことができます。

##  <a name="opennamedpipeclienttoken"></a>CAccessToken:: OpenNamedPipeClientToken

名前付きパイプに対する要求を取得するサーバー内からこのメソッドを呼び出して、クライアントからアクセストークンを使用して `CAccessToken` を初期化します。

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*hPipe*<br/>
名前付きパイプへのハンドル。

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*bImpersonate*<br/>
TRUE の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元のパイプクライアントを偽装します。 FALSE の場合、アクセストークンは開かれますが、この呼び出しが完了してもスレッドは偽装トークンを持ちません。

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティコンテキスト、または呼び出し元のスレッドのプロセスのセキュリティコンテキストに対してアクセスチェックを実行するかどうかを示します。

このパラメーターが FALSE の場合は、呼び出し元のスレッドのセキュリティコンテキストを使用してアクセスチェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティコンテキストはクライアントプロセスのものである可能性があります。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると、 *BIMPERSONATE*フラグを TRUE に設定することによって作成された偽装アクセストークンを自動的に元に戻すことができます。

##  <a name="openrpcclienttoken"></a>CAccessToken:: OpenRPCClientToken

RPC クライアントからの呼び出しを処理するサーバー内からこのメソッドを呼び出して、クライアントからアクセストークンを使用して `CAccessToken` を初期化します。

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*BindingHandle*<br/>
クライアントへのバインドを表すサーバー上のバインドハンドル。

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*bImpersonate*<br/>
TRUE の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の RPC クライアントを偽装します。 FALSE の場合、アクセストークンは開かれますが、この呼び出しが完了してもスレッドは偽装トークンを持ちません。

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティコンテキスト、または呼び出し元のスレッドのプロセスのセキュリティコンテキストに対してアクセスチェックを実行するかどうかを示します。

このパラメーターが FALSE の場合は、呼び出し元のスレッドのセキュリティコンテキストを使用してアクセスチェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティコンテキストはクライアントプロセスのものである可能性があります。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると、 *BIMPERSONATE*フラグを TRUE に設定することによって作成された偽装アクセストークンを自動的に元に戻すことができます。

##  <a name="openthreadtoken"></a>CAccessToken:: OpenThreadToken

このメソッドを呼び出して、偽装レベルを設定し、指定されたスレッドのトークンを使用して `CAccessToken` を初期化します。

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>パラメーター

*dwDesiredAccess*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*bImpersonate*<br/>
TRUE の場合、このメソッドが完了すると、スレッドは要求された偽装レベルのままになります。 FALSE の場合、スレッドは元の偽装レベルに戻ります。

*bOpenAsSelf*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティコンテキスト、または呼び出し元のスレッドのプロセスのセキュリティコンテキストに対してアクセスチェックを実行するかどうかを示します。

このパラメーターが FALSE の場合は、呼び出し元のスレッドのセキュリティコンテキストを使用してアクセスチェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティコンテキストはクライアントプロセスのものである可能性があります。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティコンテキストを使用してアクセスチェックが行われます。

*sil*<br/>
トークンの偽装レベルを提供する[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)列挙型を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`OpenThreadToken` は[CAccessToken:: GetThreadToken](#getthreadtoken)に似ていますが、スレッドのアクセストークンから `CAccessToken` を初期化する前に偽装レベルを設定します。

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると、 *BIMPERSONATE*フラグを TRUE に設定することによって作成された偽装アクセストークンを自動的に元に戻すことができます。

##  <a name="privilegecheck"></a>CAccessToken::P rivilegeCheck

このメソッドを呼び出して、`CAccessToken` オブジェクトで、指定した権限のセットが有効になっているかどうかを確認します。

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>パラメーター

*RequiredPrivileges*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set)構造体へのポインター。

*pbResult*<br/>
指定された特権のいずれかまたはすべてが `CAccessToken` オブジェクトで有効になっているかどうかを示すために、メソッドが設定する値へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`PrivilegeCheck` が返されると、対応する特権が有効になっている場合は、各[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)構造体の `Attributes` メンバーが SE_PRIVILEGE_USED_FOR_ACCESS に設定されます。 このメソッドは、 [PrivilegeCheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 関数を呼び出します。

##  <a name="revert"></a>CAccessToken:: Revert

スレッドが偽装トークンを使用しないようにするには、このメソッドを呼び出します。

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*hThread*<br/>
偽装から復帰するスレッドへのハンドル。 *Hthread*が NULL の場合、現在のスレッドが想定されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

偽装トークンの再設定は、 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用して自動的に実行できます。

##  <a name="setdefaultdacl"></a>CAccessToken:: SetDefaultDacl

`CAccessToken` オブジェクトの既定の DACL を設定するには、このメソッドを呼び出します。

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>パラメーター

*rDacl*<br/>
新しい既定の[CDacl クラス](../../atl/reference/cdacl-class.md)情報。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

既定の DACL は、このアクセストークンを有効にして新しいオブジェクトを作成するときに既定で使用される DACL です。

##  <a name="setowner"></a>CAccessToken:: SetOwner

`CAccessToken` オブジェクトの所有者を設定するには、このメソッドを呼び出します。

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
所有者情報を格納している[CSid クラス](../../atl/reference/csid-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

所有者は、このアクセストークンが有効になっている間に作成された新しいオブジェクトに使用される既定の所有者です。

##  <a name="setprimarygroup"></a>CAccessToken:: SetPrimaryGroup

`CAccessToken` オブジェクトのプライマリグループを設定するには、このメソッドを呼び出します。

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
プライマリグループ情報を格納している[CSid クラス](../../atl/reference/csid-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

プライマリグループは、このアクセストークンが有効になっている間に作成された新しいオブジェクトの既定のグループです。

## <a name="see-also"></a>参照

[ATLSecurity サンプル](../../overview/visual-cpp-samples.md)<br/>
[アクセストークン](/windows/win32/SecAuthZ/access-tokens)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
