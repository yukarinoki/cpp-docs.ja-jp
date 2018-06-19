---
title: CAccessToken クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 407652cc5a5e300a2e5eb9d6a5a07dd29209ffef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366342"
---
# <a name="caccesstoken-class"></a>CAccessToken クラス
このクラスは、アクセス トークンのラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAccessToken
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAccessToken::~CAccessToken](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAccessToken::Attach](#attach)|指定したアクセス トークンのハンドルの所有権を取得するには、このメソッドを呼び出します。|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|指定された SID が有効になっているかどうかを決定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|このメソッドを呼び出して新しい偽装アクセス トークンを作成します。|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|新しいプライマリ トークンを作成するには、このメソッドを呼び出します。|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|によって表されるユーザーのセキュリティ コンテキストで実行されている、新しいプロセスを作成するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|新しく作成するには、このメソッドを呼び出す制限`CAccessToken`オブジェクト。|  
|[CAccessToken::Detach](#detach)|アクセス トークンの所有権を取り消すには、このメソッドを呼び出します。|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|権限を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|1 つ以上の特権を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|1 つ以上の特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|返すには、このメソッドを呼び出して、`CAccessToken`オブジェクトの既定の DACL です。|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|取得するには、このメソッドを呼び出して、`CAccessToken`有効で、現在のスレッドのアクセス トークンと等しいオブジェクト。|  
|[CAccessToken::GetGroups](#getgroups)|返すには、このメソッドを呼び出して、`CAccessToken`トークンのオブジェクトのグループです。|  
|[CAccessToken::GetHandle](#gethandle)|アクセス トークンへのハンドルを取得するには、このメソッドを呼び出します。|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|アクセス トークンから偽装レベルを取得するには、このメソッドを呼び出します。|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|関連付けられたログオン セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetLogonSid](#getlogonsid)|関連付けられたログオン SID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetOwner](#getowner)|関連付けられている所有者を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|関連付けられているプライマリ グループを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetPrivileges](#getprivileges)|関連付けられている特権を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。|  
|[CAccessToken::GetProfile](#getprofile)|関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetSource](#getsource)|ソースを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetStatistics](#getstatistics)|関連付けられている情報を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|関連付けられているターミナル サービス セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|初期化するためにこのメソッドを呼び出して、`CAccessToken`の特定のスレッドからトークンを使用します。|  
|[CAccessToken::GetTokenId](#gettokenid)|関連付けられているトークンの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetType](#gettype)|トークンの種類を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::GetUser](#getuser)|関連付けられているユーザーを識別するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::Impersonate](#impersonate)|権限の借用を割り当てるには、このメソッドを呼び出す`CAccessToken`スレッドにします。|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|ログオン ユーザーのセキュリティ コンテキストを偽装する呼び出し元のスレッドを許可するには、このメソッドを呼び出します。|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|場合は、テストするには、このメソッドを呼び出す、`CAccessToken`オブジェクトには、制限付きの Sid の一覧が含まれています。|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|このメソッドに関連付けられているユーザー プロファイルの読み込みを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::LogonUser](#logonuser)|指定された資格情報に関連付けられているユーザーのログオン セッションを作成するには、このメソッドを呼び出します。|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|初期化するために、クライアントからの呼び出しを処理、COM サーバー内からこのメソッドを呼び出して、`CAccessToken`の COM クライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|初期化するために、名前付きパイプ経由でこのメソッドは、サーバー内から取得要求を呼び出して、`CAccessToken`のクライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|初期化するために、RPC クライアントからの呼び出しを処理するサーバー内からこのメソッドを呼び出して、`CAccessToken`のクライアントからアクセス トークンを使用します。|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|偽装レベルを設定し、初期化するには、このメソッドを呼び出す、`CAccessToken`の特定のスレッドからトークンを使用します。|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|指定された権限のセットが有効かどうかを確認するには、このメソッドを呼び出して、 **CAccessToken**オブジェクト。|  
|[CAccessToken::Revert](#revert)|権限借用トークンを使用しているスレッドを停止するには、このメソッドを呼び出します。|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|既定値を設定するには、このメソッドを呼び出すの DACL、`CAccessToken`オブジェクト。|  
|[CAccessToken::SetOwner](#setowner)|所有者を設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|プライマリ グループを設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)プロセスまたはスレッドのセキュリティ コンテキストを記述し、Windows システムにログオンしている各ユーザーに割り当てられているオブジェクトです。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="attach"></a>  CAccessToken::Attach  
 指定したアクセス トークンのハンドルの所有権を取得するには、このメソッドを呼び出します。  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *hToken*  
 アクセス トークンへのハンドル。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合、`CAccessToken`オブジェクトには、アクセス トークンの所有権が既に存在します。  
  
##  <a name="dtor"></a>  CAccessToken:: ~ CAccessToken  
 デストラクターです。  
  
```
virtual ~CAccessToken() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership  
 指定された SID が有効になっているかどうかを決定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool CheckTokenMembership(
    const CSid& rSid, 
    bool* pbIsMember) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 参照、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクト。  
  
 `pbIsMember`  
 チェックの結果を受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CheckTokenMembership`メソッドは、ユーザーとグループの Sid、アクセス トークンの SID の存在を確認します。 SID が存在し、SE_GROUP_ENABLED 属性を持つ場合*pbIsMember*にそれ以外の場合は true を設定するには、false に設定されています。  
  
 デバッグ ビルドで、アサーション エラーが発生場合`pbIsMember`有効なポインターではありません。  
  
> [!NOTE]
>  `CAccessToken`偽装トークンと、プライマリ トークンではないオブジェクトがある必要があります。  
  
##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken  
 偽装アクセス トークンを作成するには、このメソッドを呼び出します。  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImp`  
 新しいポインター`CAccessToken`オブジェクト。  
  
 `sil`  
 指定します、 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)新しいトークンの偽装レベルを提供する型を列挙します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateImpersonationToken` 呼び出し[DuplicateToken](http://msdn.microsoft.com/library/windows/desktop/aa446616)新しい権限借用トークンを作成します。  
  
##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken  
 新しいプライマリ トークンを作成するには、このメソッドを呼び出します。  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPri*  
 新しいポインター`CAccessToken`オブジェクト。  
  
 `dwDesiredAccess`  
 新しいトークンの要求されたアクセス権を指定します。 MAXIMUM_ALLOWED、既定では、呼び出し元の有効なすべてのアクセス権を要求します。 参照してください[アクセス権とアクセス マスク](http://msdn.microsoft.com/library/windows/desktop/aa374902)の詳細にアクセス権。  
  
 *pTokenAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体を新しいトークンのセキュリティ記述子を指定し、子プロセスがトークンを継承できるかどうかを判定します。 場合*pTokenAttributes* NULL トークンが既定のセキュリティ記述子を取得、ハンドルは継承できません。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreatePrimaryToken` 呼び出し[DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617)を新しいプライマリ トークンを作成します。  
  
##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser  
 によって表されるユーザーのセキュリティ コンテキストで実行されている、新しいプロセスを作成するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
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
 *pApplicationName*  
 実行するモジュールを指定する null で終わる文字列へのポインター。 このパラメーターは、NULL をできない可能性があります。  
  
 *pCommandLine*  
 実行するコマンドラインを指定する null で終わる文字列へのポインター。  
  
 *pProcessInformation*  
 ポインター、[ハンドル](http://msdn.microsoft.com/library/windows/desktop/ms684873)が新しいプロセスの識別情報を受け取る。  
  
 *pStartupInfo*  
 ポインター、 [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331)構造が新しいプロセスのメイン ウィンドウの表示方法を指定します。  
  
 `dwCreationFlags`  
 優先順位クラスと、プロセスの作成を制御する追加のフラグを指定します。 Win32 関数を参照して[CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429)フラグの一覧についてはします。  
  
 *bLoadProfile*  
 True のかどうか、ユーザーのプロファイルがで読み込まれます[LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281)です。  
  
 *pProcessAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造が新しいプロセスのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承できるかどうかを判断します。 場合*pProcessAttributes* null、プロセスは、既定のセキュリティ記述子を取得およびハンドルは継承できません。  
  
 *pThreadAttributes*  
 ポインター、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造を新しいスレッドのセキュリティ記述子を指定し、返されたハンドルを子プロセスが継承できるかどうかを判定します。 場合*pThreadAttributes* null、スレッドは、既定のセキュリティ記述子を取得およびハンドルは継承できません。  
  
 *bInherit*  
 新しいプロセスが呼び出しプロセスからハンドルを継承するかどうかを示します。 True の場合、呼び出し元のプロセスで継承可能な各開いているハンドルは、新しいプロセスによって継承されます。 継承されたハンドルは、元のハンドルと同じ値とアクセス特権を持っています。  
  
 *pCurrentDirectory*  
 現在のドライブと、新しいプロセス用のディレクトリを指定する null で終わる文字列へのポインター。 文字列は、ドライブ文字を含む完全なパスである必要があります。 このパラメーターが NULL の場合、新しいプロセスは、呼び出し元プロセスとして同じ現在のドライブとディレクトリがあります。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 **CreateProcessAsUser**を使用して、`CreateProcessAsUser`によって表されるユーザーのセキュリティ コンテキストで実行される新しいプロセスを作成する Win32 関数、`CAccessToken`オブジェクト。 説明を参照して、 [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429)関数に必要なパラメーターの詳細。  
  
 このメソッドが成功するため、 `CAccessToken` (制限付きトークンである) 場合を除き、オブジェクトは AssignPrimaryToken を保持する必要があります実行します。  
  
##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken  
 新しく作成するには、このメソッドを呼び出す制限`CAccessToken`オブジェクト。  
  
```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRestrictedToken*  
 新しい制限`CAccessToken`オブジェクト。  
  
 `SidsToDisable`  
 A`CTokenGroups`拒否専用 Sid を指定するオブジェクト。  
  
 *SidsToRestrict*  
 A `CTokenGroups` Sid を制限を指定するオブジェクト。  
  
 `PrivilegesToDelete`  
 A`CTokenPrivileges`制限付きトークンで削除する権限を指定するオブジェクト。 既定値は、空のオブジェクトを作成します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `CreateRestrictedToken` 使用して、 [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) Win32 関数を作成、新しい`CAccessToken`オブジェクトを制限します。  
  
> [!IMPORTANT]
>  使用する場合`CreateRestrictedToken`、以下を確認する: 既存のトークンは有効な (かつ、ユーザーが入っていない) および`SidsToDisable`と`PrivilegesToDelete`が有効 (かつ、ユーザーが入っていない)。 メソッドが false を返す場合は、機能を拒否します。  
  
##  <a name="detach"></a>  CAccessToken::Detach  
 アクセス トークンの所有権を取り消すには、このメソッドを呼び出します。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返します、`CAccessToken`がデタッチされます。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは失効、`CAccessToken`のアクセス トークンの所有者。  
  
##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege  
 権限を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 無効にするための権限を含む文字列へのポインター、`CAccessToken`オブジェクト。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges  
 1 つ以上の特権を無効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPrivileges`  
 無効にするための特権を含む文字列の配列へのポインター、`CAccessToken`オブジェクト。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege  
 特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszPrivilege`  
 有効にするための権限を含む文字列へのポインター、`CAccessToken`オブジェクト。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges  
 1 つ以上の特権を有効にするには、このメソッドを呼び出す、`CAccessToken`オブジェクト。  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPrivileges`  
 有効にするための特権を含む文字列の配列へのポインター、`CAccessToken`オブジェクト。  
  
 `pPreviousState`  
 ポインター、`CTokenPrivileges`特権の以前の状態を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl  
 返すには、このメソッドを呼び出して、`CAccessToken`オブジェクトの既定の DACL です。  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDacl`  
 ポインター、 [CDacl クラス](../../atl/reference/cdacl-class.md)オブジェクトを受け取る、 **CAccessToken**オブジェクトの既定の DACL です。  
  
### <a name="return-value"></a>戻り値  
 既定の DACL があった場合、回復は false それ以外の場合は true を返します。  
  
##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken  
 取得するには、このメソッドを呼び出して、`CAccessToken`有効で、現在のスレッドのアクセス トークンと等しいオブジェクト。  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getgroups"></a>  CAccessToken::GetGroups  
 返すには、このメソッドを呼び出して、`CAccessToken`トークンのオブジェクトのグループです。  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pGroups*  
 ポインター、 [CTokenGroups クラス](../../atl/reference/ctokengroups-class.md)グループ情報を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gethandle"></a>  CAccessToken::GetHandle  
 アクセス トークンへのハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetHandle() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返します、`CAccessToken`オブジェクトのアクセス トークン。  
  
##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel  
 アクセス トークンから偽装レベルを取得するには、このメソッドを呼び出します。  
  
```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pImpersonationLevel*  
 ポインター、 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)偽装レベルの情報を受け取る列挙型。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId  
 関連付けられたログオン セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pluid`  
 ポインター、 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)ログオン セッション ID が表示されます  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`pluid`無効な値です。  
  
##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid  
 関連付けられたログオン SID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生*pSid*無効な値です。  
  
##  <a name="getowner"></a>  CAccessToken::GetOwner  
 関連付けられている所有者を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 所有者は、既定ではこのアクセス トークンが有効なときに作成されたオブジェクトに設定されます。  
  
##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup  
 関連付けられているプライマリ グループを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 グループは、既定ではこのアクセス トークンが有効なときに作成されたオブジェクトに設定されます。  
  
##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges  
 関連付けられている特権を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPrivileges`  
 ポインター、 [CTokenPrivileges クラス](../../atl/reference/ctokenprivileges-class.md)権限を受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken  
 指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 *hProcess*  
 アクセス トークンが開いているプロセスへのハンドル。 `NULL` の既定値を使用すると、現在のプロセスが使用されます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`true` を返します。それ以外の場合は、`false` を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し、 [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) Win32 関数。  
  
##  <a name="getprofile"></a>  CAccessToken::GetProfile  
 関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロファイルが存在しない場合、ユーザー プロファイル、または NULL を指すハンドルを返します。  
  
##  <a name="getsource"></a>  CAccessToken::GetSource  
 ソースを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSource*  
 ポインター、 [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getstatistics"></a>  CAccessToken::GetStatistics  
 関連付けられている情報を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStatistics*  
 ポインター、 [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId  
 関連付けられているターミナル サービス セッションの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwSessionId*  
 ターミナル サービス セッション id です。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken  
 初期化するためにこのメソッドを呼び出して、`CAccessToken`の特定のスレッドからトークンを使用します。  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `hThread`  
 アクセス トークンが開かれているスレッドへのハンドルします。  
  
 `bOpenAsSelf`  
 アクセス チェックが、スレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、`GetThreadToken`メソッド、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドでは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gettokenid"></a>  CAccessToken::GetTokenId  
 関連付けられているトークンの ID を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pluid`  
 ポインター、 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)トークンの ID が表示されます  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="gettype"></a>  CAccessToken::GetType  
 トークンの種類を取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pType`  
 アドレス、 [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633)成功した場合、トークンの種類を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 **TOKEN_TYPE**列挙型には、プライマリ トークンと権限借用トークンを区別する値が含まれています。  
  
##  <a name="getuser"></a>  CAccessToken::GetUser  
 関連付けられているユーザーを識別するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid クラス](../../atl/reference/csid-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser  
 関連付けられたユーザー プロファイルを指すハンドルを取得するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロファイルが存在しない場合、ユーザー プロファイル、または NULL を指すハンドルを返します。  
  
##  <a name="impersonate"></a>  CAccessToken::Impersonate  
 権限の借用を割り当てるには、このメソッドを呼び出す`CAccessToken`スレッドにします。  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hThread`  
 スレッドの偽装トークンを割り当てるへのハンドルします。 TOKEN_IMPERSONATE アクセス権を持つこのハンドルが開かれている必要があります。 場合`hThread`が NULL の場合、メソッドによって、スレッドの偽装トークンの使用を停止します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合`CAccessToken`をトークンに有効なポインターはありません。  
  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)権限を借用したアクセス トークンを自動的に戻すには使用できます。  
  
##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser  
 ログオン ユーザーのセキュリティ コンテキストを偽装する呼び出し元のスレッドを許可するには、このメソッドを呼び出します。  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
>  偽装関数への呼び出しは、何らかの理由で失敗すると場合、クライアントを偽装できませんし、クライアントが要求呼び出しを行ったプロセスのセキュリティ コンテキストでします。 場合は、プロセスが、高い特権を持つアカウントとして実行されているまたは管理グループのメンバーは、ユーザーがアクションを実行することがありますか通常は許可されません。 そのため、この関数の戻り値常に確認する必要があります。  
  
##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted  
 場合は、テストするには、このメソッドを呼び出す、`CAccessToken`オブジェクトには、制限付きの Sid の一覧が含まれています。  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトには、Sid、Sid を制限がない場合は、false の制限の一覧が含まれている場合、またはメソッドが失敗した場合は true を返します。  
  
##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile  
 このメソッドに関連付けられているユーザー プロファイルの読み込みを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合、`CAccessToken`有効なトークンが含まれていないか、または、ユーザーは既にプロファイルがします。  
  
##  <a name="logonuser"></a>  CAccessToken::LogonUser  
 指定された資格情報に関連付けられているユーザーのログオン セッションを作成するには、このメソッドを呼び出します。  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszUserName`  
 ユーザー名を指定する null で終わる文字列へのポインター。 これにログオンするユーザー アカウントの名前です。  
  
 *pszDomain*  
 ドメインまたはのアカウント データベースを含むサーバーの名前を指定する null で終わる文字列へのポインター、`pszUserName`アカウント。  
  
 `pszPassword`  
 指定されたユーザー アカウントのクリア テキスト パスワードを指定する null で終わる文字列へのポインター`pszUserName`です。  
  
 *dwLogonType*  
 実行するログオン操作の種類を指定します。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)詳細についてはします。  
  
 *dwLogonProvider*  
 ログオンのプロバイダーを指定します。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 関連付けられる、ログオンによるトークン アクセス、`CAccessToken`です。 このメソッドが成功するため、`CAccessToken`オブジェクトの所有者を識別する基本の信頼されたコンピューターの一部として、SE_TCB_NAME 特権を保持する必要があります。 参照してください[LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184)必要な権限に関する詳細についてはします。  
  
##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken  
 初期化するために、クライアントからの呼び出しを処理、COM サーバー内からこのメソッドを呼び出して、`CAccessToken`の COM クライアントからアクセス トークンを使用します。  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の COM クライアントを偽装します。 False の場合、アクセス トークンが開かれると、けれども、この呼び出しが完了したときに、スレッドは、権限借用トークンをありません。  
  
 `bOpenAsSelf`  
 アクセス チェックが、スレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッド、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドでは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)できますを使用して自動的に設定して作成した権限を借用したアクセス トークンを戻す、`bImpersonate`フラグを*true*です。  
  
##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken  
 初期化するために、名前付きパイプ経由でこのメソッドは、サーバー内から取得要求を呼び出して、`CAccessToken`のクライアントからアクセス トークンを使用します。  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPipe*  
 名前付きパイプへのハンドルします。  
  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元のパイプ クライアントを偽装します。 False の場合、アクセス トークンが開かれると、けれども、この呼び出しが完了したときに、スレッドは、権限借用トークンをありません。  
  
 `bOpenAsSelf`  
 アクセス チェックが、スレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッド、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドでは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)できますを使用して自動的に設定して作成した権限を借用したアクセス トークンを戻す、`bImpersonate`フラグを*true*です。  
  
##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken  
 初期化するために、RPC クライアントからの呼び出しを処理するサーバー内からこのメソッドを呼び出して、`CAccessToken`のクライアントからアクセス トークンを使用します。  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *BindingHandle*  
 クライアントへのバインドを表す、サーバーに対するハンドルをバインドします。  
  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出し元の RPC クライアントを偽装します。 False の場合、アクセス トークンが開かれると、けれども、この呼び出しが完了したときに、スレッドは、権限借用トークンをありません。  
  
 `bOpenAsSelf`  
 アクセス チェックが、スレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッド、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドでは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)できますを使用して自動的に設定して作成した権限を借用したアクセス トークンを戻す、`bImpersonate`フラグを*true*です。  
  
##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken  
 偽装レベルを設定し、初期化するには、このメソッドを呼び出す、`CAccessToken`の特定のスレッドからトークンを使用します。  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDesiredAccess`  
 アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。  
  
 `bImpersonate`  
 True の場合、メソッドの完了後に、スレッド名は、要求された偽装レベルに残すあります。 False の場合、スレッドは元の偽装レベルに戻ります。  
  
 `bOpenAsSelf`  
 アクセス チェックが、スレッドの呼び出し元のセキュリティ コンテキストに対して行われるかどうかを示す、 [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182)メソッド、または呼び出し元のスレッドのプロセスのセキュリティ コンテキスト。  
  
 このパラメーターが false の場合は、呼び出し元のスレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドでは、クライアントを偽装する場合、クライアント プロセスのことをこのセキュリティ コンテキストにできます。 このパラメーターが true の場合、呼び出し元のスレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックを実行します。  
  
 `sil`  
 指定します、 [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572)トークンの偽装レベルを提供する型を列挙します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 `OpenThreadToken` に似ていますが[CAccessToken::GetThreadToken](#getthreadtoken)、初期化する前に、偽装レベルを設定が、`CAccessToken`スレッドのアクセス トークンから。  
  
 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)できますを使用して自動的に設定して作成した権限を借用したアクセス トークンを戻す、`bImpersonate`フラグを*true*です。  
  
##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck  
 指定された権限のセットが有効かどうかを確認するには、このメソッドを呼び出して、 **CAccessToken**オブジェクト。  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *RequiredPrivileges*  
 ポインター、 [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307)構造体。  
  
 *pbResult*  
 値へのポインターで指定した権限の一部またはすべてが有効にするかどうかを示すために、メソッドを設定、`CAccessToken`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 ときに`PrivilegeCheck`が返される、**属性**のそれぞれに所属[LUID_AND_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)対応する権限が有効になっている場合は、構造体を SE_PRIVILEGE_USED_FOR_ACCESS に設定します。 このメソッドは、 [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) Win32 関数。  
  
##  <a name="revert"></a>  CAccessToken::Revert  
 権限借用トークンを使用してスレッドを停止するには、このメソッドを呼び出します。  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hThread`  
 権限借用を戻すには、スレッドへのハンドルします。 場合*hThread* NULL の場合は、現在のスレッドが使用されます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 権限借用トークンのバージョンを再設定を自動的に実行することができます、 [CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)です。  
  
##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl  
 既定値を設定するには、このメソッドを呼び出すの DACL、`CAccessToken`オブジェクト。  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rDacl`  
 新しい既定[CDacl クラス](../../atl/reference/cdacl-class.md)情報。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 既定の DACL は、新しいオブジェクトがこのアクセス トークンが有効で作成されるときに既定で使用される DACL です。  
  
##  <a name="setowner"></a>  CAccessToken::SetOwner  
 所有者を設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid クラス](../../atl/reference/csid-class.md)所有者情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 所有者は、このアクセス トークンが有効なときに作成された新しいオブジェクトに使用される既定の所有者です。  
  
##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup  
 プライマリ グループを設定するには、このメソッドを呼び出して、`CAccessToken`オブジェクト。  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rSid`  
 [CSid クラス](../../atl/reference/csid-class.md)プライマリ グループ情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 プライマリ グループは、このアクセス トークンが有効なときに作成された新しいオブジェクトの既定のグループです。  
  
## <a name="see-also"></a>関連項目  
 [ATLSecurity サンプル](../../visual-cpp-samples.md)   
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [クラスの概要](../../atl/atl-class-overview.md)
