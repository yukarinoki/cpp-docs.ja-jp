---
title: クラス
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
ms.openlocfilehash: 9ae63946dfa6244e97c376f9eccd9bab93586990
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319039"
---
# <a name="caccesstoken-class"></a>クラス

このクラスは、アクセス トークンのラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAccessToken
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の項目を使用します。](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を使用します。](#attach)|指定したアクセス トークン ハンドルの所有権を取得します。|
|[次の項目を確認します。](#checktokenmembership)|`CAccessToken`オブジェクトで指定した SID が有効かどうかを確認します。|
|[をクリックします。](#createimpersonationtoken)|新しい偽装アクセス トークンを作成します。|
|[次の項目を使用します。](#createprimarytoken)|新しいプライマリ トークンを作成します。|
|[を使用します。](#createprocessasuser)|オブジェクトによって表されるユーザーのセキュリティ コンテキストで実行される新しいプロセスを`CAccessToken`作成します。|
|[を制限するトークン](#createrestrictedtoken)|このメソッドを呼び出して、新しい`CAccessToken`制限付きオブジェクトを作成します。|
|[アクセストークン::Dエタッハ](#detach)|アクセス トークンの所有権を取り消します。|
|[:D可能な特権](#disableprivilege)|`CAccessToken`オブジェクトの特権を無効にします。|
|[次の特権を:D](#disableprivileges)|オブジェクトの 1 つ以上の特権を無効`CAccessToken`にします。|
|[次のコマンドを実行します。](#enableprivilege)|`CAccessToken`オブジェクト内の特権を有効にします。|
|[次の特権を有効にします。](#enableprivileges)|オブジェクトの 1 つ以上の特権を有効`CAccessToken`にします。|
|[を取得します。](#getdefaultdacl)|オブジェクトの既定の DACL を`CAccessToken`返します。|
|[を使用します。](#geteffectivetoken)|現在のスレッドに対して`CAccessToken`有効なアクセス トークンと同じオブジェクトを取得します。|
|[次の項目を取得します。](#getgroups)|オブジェクトのトークン グループを`CAccessToken`返します。|
|[を取得します。](#gethandle)|アクセス トークンへのハンドルを取得します。|
|[を取得します。](#getimpersonationlevel)|アクセス トークンから偽装レベルを取得します。|
|[をクリックします。](#getlogonsessionid)|オブジェクトに関連付けられたログオン セッション ID を`CAccessToken`取得します。|
|[をクリックします。](#getlogonsid)|`CAccessToken`オブジェクトに関連付けられたログオン SID を取得します。|
|[を取得します。](#getowner)|オブジェクトに関連付けられている所有者を取得します`CAccessToken`。|
|[次の項目を取得します。](#getprimarygroup)|`CAccessToken`オブジェクトに関連付けられているプライマリ グループを取得します。|
|[次の項目を取得します。](#getprivileges)|`CAccessToken`オブジェクトに関連付けられている特権を取得します。|
|[を使用します。](#getprocesstoken)|指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。|
|[を見る](#getprofile)|`CAccessToken`オブジェクトに関連付けられたユーザー プロファイルを指すハンドルを取得します。|
|[次の項目を使用します。](#getsource)|`CAccessToken`オブジェクトのソースを取得します。|
|[次の項目を取得します。](#getstatistics)|オブジェクトに関連付けられた情報を`CAccessToken`取得します。|
|[を指定します。](#getterminalservicessessionid)|オブジェクトに関連付けられているターミナル サービス セッション ID`CAccessToken`を取得します。|
|[を返します。](#getthreadtoken)|指定したスレッドのトークンを`CAccessToken`使用して を初期化します。|
|[を返します。](#gettokenid)|`CAccessToken`オブジェクトに関連付けられたトークン ID を取得します。|
|[次の値を取得します。](#gettype)|`CAccessToken`オブジェクトのトークンの種類を取得します。|
|[次の操作を行います。](#getuser)|`CAccessToken`オブジェクトに関連付けられているユーザーを識別します。|
|[キートークン::キーカレントユーザー](#hkeycurrentuser)|`CAccessToken`オブジェクトに関連付けられたユーザー プロファイルを指すハンドルを取得します。|
|[偽装](#impersonate)|スレッドに偽装`CAccessToken`を割り当てます。|
|[を偽装する](#impersonateloggedonuser)|呼び出し元のスレッドがログオンユーザーのセキュリティ コンテキストを偽装できるようにします。|
|[アクセストークン::IsToken制限](#istokenrestricted)|オブジェクトに制限付き`CAccessToken`の SID のリストが含まれているかどうかをテストします。|
|[を読み込む](#loaduserprofile)|`CAccessToken`オブジェクトに関連付けられているユーザー プロファイルを読み込みます。|
|[次の操作を行います。](#logonuser)|指定された資格情報に関連付けられたユーザーのログオン セッションを作成します。|
|[をクリックします。](#opencomclienttoken)|このメソッドは、クライアントからの呼び出しを処理する COM サーバー内`CAccessToken`から呼び出して、COM クライアントからのアクセス トークンを使用して を初期化します。|
|[をクリックします。](#opennamedpipeclienttoken)|サーバー内からこのメソッドを呼び出し、名前付きパイプを`CAccessToken`介して要求を受け取って、クライアントからのアクセス トークンを使用して を初期化します。|
|[をクリックします。](#openrpcclienttoken)|このメソッドは、RPC クライアントからの呼び出しを処理するサーバー内から`CAccessToken`呼び出して、クライアントからのアクセス トークンを使用して を初期化します。|
|[をクリックします。](#openthreadtoken)|偽装レベルを設定し、指定したスレッドのトークンを`CAccessToken`使用して を初期化します。|
|[:Pリビレゲチェック](#privilegecheck)|オブジェクトで`CAccessToken`指定された特権セットが有効かどうかを調べます。|
|[アクセストークン::元に戻す](#revert)|偽装トークンを使用しているスレッドを停止します。|
|[を設定します。](#setdefaultdacl)|`CAccessToken`オブジェクトの既定の DACL を設定します。|
|[を指定します。](#setowner)|`CAccessToken`オブジェクトの所有者を設定します。|
|[を設定します。](#setprimarygroup)|`CAccessToken`オブジェクトのプライマリ グループを設定します。|

## <a name="remarks"></a>解説

[アクセス トークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティ コンテキストを記述するオブジェクトで、Windows システムにログオンしている各ユーザーに割り当てられます。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="caccesstokenattach"></a><a name="attach"></a>次の項目を使用します。

指定したアクセス トークン ハンドルの所有権を取得します。

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>パラメーター

*hトークン*<br/>
アクセス トークンへのハンドル。

### <a name="remarks"></a>解説

デバッグ ビルドでは、オブジェクトがアクセス トークンの`CAccessToken`所有権を既に持っている場合、アサーション エラーが発生します。

## <a name="caccesstokencaccesstoken"></a><a name="dtor"></a>次の項目を使用します。

デストラクターです。

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="caccesstokenchecktokenmembership"></a><a name="checktokenmembership"></a>次の項目を確認します。

`CAccessToken`オブジェクトで指定した SID が有効かどうかを確認します。

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへの参照。

*メンバー*<br/>
チェックの結果を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

この`CheckTokenMembership`メソッドは、アクセス トークンのユーザーおよびグループ SID に SID が存在するかどうかチェックします。 SID が存在し、SE_GROUP_ENABLED属性を持つ場合 *、pbIsMember*は TRUE に設定されます。それ以外の場合は FALSE に設定されます。

デバッグ ビルドでは *、pbIsMember*が有効なポインターでない場合、アサーション エラーが発生します。

> [!NOTE]
> オブジェクト`CAccessToken`は、プライマリ トークンではなく偽装トークンである必要があります。

## <a name="caccesstokencreateimpersonationtoken"></a><a name="createimpersonationtoken"></a>をクリックします。

偽装アクセス トークンを作成します。

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pImp*<br/>
新しい`CAccessToken`オブジェクトへのポインター。

*Sil*<br/>
新しいトークンの偽装レベルを提供する[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)列挙型を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateImpersonationToken`新しい偽装トークンを作成するために[重複トークン](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken)を呼び出します。

## <a name="caccesstokencreateprimarytoken"></a><a name="createprimarytoken"></a>次の項目を使用します。

新しいプライマリ トークンを作成します。

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pPri*<br/>
新しい`CAccessToken`オブジェクトへのポインター。

*アクセスを許可*<br/>
新しいトークンに対して要求されたアクセス権を指定します。 デフォルトのMAXIMUM_ALLOWEDは、呼び出し元に対して有効なすべてのアクセス権を要求します。 [アクセス権の詳細については、「アクセス権とアクセスマスク](/windows/win32/SecAuthZ/access-rights-and-access-masks)」を参照してください。

*属性*<br/>
新しいトークンのセキュリティ記述子を指定し、子プロセスがトークンを継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *pTokenAttributes*が NULL の場合、トークンは既定のセキュリティ記述子を取得し、ハンドルを継承できません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreatePrimaryToken`新しいプライマリ トークンを作成するために[呼](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex)び出します。

## <a name="caccesstokencreateprocessasuser"></a><a name="createprocessasuser"></a>を使用します。

オブジェクトによって表されるユーザーのセキュリティ コンテキストで実行される新しいプロセスを`CAccessToken`作成します。

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

*アプリケーション名*<br/>
実行するモジュールを指定する null で終わる文字列へのポインター。 このパラメータは NULL にできません。

*コマンドライン*<br/>
実行するコマンド ラインを指定する null で終わる文字列へのポインター。

*をクリックします。*<br/>
新しいプロセスに関する識別情報を受け取る[PROCESS_INFORMATION構造体](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information)へのポインター。

*をクリックします。*<br/>
新しいプロセスのメイン ウィンドウの表示方法を指定する[STARTUPINFO](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow)構造体へのポインター。

*フラグを作成します。*<br/>
優先順位クラスおよびプロセスの作成を制御する追加のフラグを指定します。 フラグの一覧については、Win32 関数[CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw)を参照してください。

*プロファイルを読み込む*<br/>
TRUE の場合、ユーザーのプロファイルは[LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)で読み込まれます。

*属性*<br/>
新しいプロセスのセキュリティ記述子を指定し、子プロセスが返されたハンドルを継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *pProcessAttributes が*NULL の場合、プロセスは既定のセキュリティ記述子を取得し、ハンドルを継承できません。

*属性*<br/>
新しいスレッドのセキュリティ記述子を指定し、子プロセスが返されたハンドルを継承できるかどうかを決定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポインター。 *pThreadAttributes*が NULL の場合、スレッドは既定のセキュリティ記述子を取得し、ハンドルを継承できません。

*継承*<br/>
新しいプロセスが呼び出し元のプロセスからハンドルを継承するかどうかを示します。 TRUE の場合、呼び出し元プロセス内の各継承可能なオープン ハンドルは、新しいプロセスによって継承されます。 継承されたハンドルは、元のハンドルと同じ値とアクセス権限を持ちます。

*をクリックします。*<br/>
新しいプロセスの現在のドライブとディレクトリを指定する、NULL で終わる文字列へのポインター。 この文字列は、ドライブ文字を含む完全パスである必要があります。 このパラメータが NULL の場合、新しいプロセスは、呼び出し元のプロセスと同じ現在のドライブとディレクトリを持ちます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateProcessAsUser`Win32 関数を`CreateProcessAsUser`使用して、オブジェクトによって表されるユーザーのセキュリティ コンテキストで実行される新しい`CAccessToken`プロセスを作成します。 必要なパラメーターの詳細については[、CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw)関数の説明を参照してください。

このメソッドを成功させるには、オブジェクト`CAccessToken`が AssignPrimaryToken (制限されたトークンでない限り) と増額クォータの特権を保持する必要があります。

## <a name="caccesstokencreaterestrictedtoken"></a><a name="createrestrictedtoken"></a>を制限するトークン

このメソッドを呼び出して、新しい`CAccessToken`制限付きオブジェクトを作成します。

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>パラメーター

*制限されたトークン*<br/>
新しい制限付き`CAccessToken`オブジェクト。

*シッズト無効化*<br/>
拒否`CTokenGroups`専用の ID を指定するオブジェクト。

*シズト制限*<br/>
制限`CTokenGroups`する SID を指定するオブジェクト。

*削除する特権*<br/>
制限`CTokenPrivileges`付きトークン内の削除権限を指定するオブジェクト。 既定値では、空のオブジェクトが作成されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`CreateRestrictedToken`は、[制限付](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken)きの新しい`CAccessToken`オブジェクトを作成するために、Win32 関数を使用します。

> [!IMPORTANT]
> を使用`CreateRestrictedToken`する場合は、既存のトークンが有効 (ユーザーが入力されていない) および*SidsToDisable*と*PrivilegesToDelete*の両方が有効 (ユーザーによって入力されていない) であることを確認します。 メソッドが FALSE を返す場合は、機能を拒否します。

## <a name="caccesstokendetach"></a><a name="detach"></a>アクセストークン::Dエタッハ

アクセス トークンの所有権を取り消します。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

デタッチされた ハンドル`CAccessToken`を返します。

### <a name="remarks"></a>解説

このメソッドは、`CAccessToken`アクセス トークンの所有権を取り消します。

## <a name="caccesstokendisableprivilege"></a><a name="disableprivilege"></a>:D可能な特権

`CAccessToken`オブジェクトの特権を無効にします。

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*プリビレッジ*<br/>
オブジェクトで無効にする特権を含む文字列への`CAccessToken`ポインター。

*状態を確認する*<br/>
特権の`CTokenPrivileges`以前の状態を含むオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokendisableprivileges"></a><a name="disableprivileges"></a>次の特権を:D

オブジェクトの 1 つ以上の特権を無効`CAccessToken`にします。

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*r特典*<br/>
オブジェクトで無効にする特権を含む文字列の`CAccessToken`配列へのポインター。

*状態を確認する*<br/>
特権の`CTokenPrivileges`以前の状態を含むオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokenenableprivilege"></a><a name="enableprivilege"></a>次のコマンドを実行します。

`CAccessToken`オブジェクト内の特権を有効にします。

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*プリビレッジ*<br/>
オブジェクトで有効にする特権を含む文字列への`CAccessToken`ポインター。

*状態を確認する*<br/>
特権の`CTokenPrivileges`以前の状態を含むオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokenenableprivileges"></a><a name="enableprivileges"></a>次の特権を有効にします。

オブジェクトの 1 つ以上の特権を有効`CAccessToken`にします。

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*r特典*<br/>
`CAccessToken`オブジェクトで有効にする特権を含む文字列の配列へのポインター。

*状態を確認する*<br/>
特権の`CTokenPrivileges`以前の状態を含むオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetdefaultdacl"></a><a name="getdefaultdacl"></a>を取得します。

オブジェクトの既定の DACL を`CAccessToken`返します。

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pDacl*<br/>
オブジェクトの既定の DACL を受け取`CAccessToken`る[CDacl クラス](../../atl/reference/cdacl-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

既定の DACL が回復された場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="caccesstokengeteffectivetoken"></a><a name="geteffectivetoken"></a>を使用します。

現在のスレッドに対して`CAccessToken`有効なアクセス トークンと同じオブジェクトを取得します。

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>パラメーター

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetgroups"></a><a name="getgroups"></a>次の項目を取得します。

オブジェクトのトークン グループを`CAccessToken`返します。

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>パラメーター

*グループ*<br/>
グループ情報を受け取る[CTokenGroups クラス](../../atl/reference/ctokengroups-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengethandle"></a><a name="gethandle"></a>を取得します。

アクセス トークンへのハンドルを取得します。

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトのアクセス トークン`CAccessToken`へのハンドルを返します。

## <a name="caccesstokengetimpersonationlevel"></a><a name="getimpersonationlevel"></a>を取得します。

アクセス トークンから偽装レベルを取得します。

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>パラメーター

*を変更します。*<br/>
偽装レベル情報を受け取る[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)列挙型へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetlogonsessionid"></a><a name="getlogonsessionid"></a>をクリックします。

オブジェクトに関連付けられたログオン セッション ID を`CAccessToken`取得します。

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*プルイド*<br/>
ログオン セッション ID を受け取る[LUID](/windows/win32/api/winnt/ns-winnt-luid)へのポインタ。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、pluid*が無効な値である場合、アサーション エラーが発生します。

## <a name="caccesstokengetlogonsid"></a><a name="getlogonsid"></a>をクリックします。

`CAccessToken`オブジェクトに関連付けられたログオン SID を取得します。

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、pSid*が無効な値である場合、アサーション エラーが発生します。

## <a name="caccesstokengetowner"></a><a name="getowner"></a>を取得します。

オブジェクトに関連付けられている所有者を取得します`CAccessToken`。

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

所有者は、このアクセス トークンが有効な間に作成されたオブジェクトに既定で設定されます。

## <a name="caccesstokengetprimarygroup"></a><a name="getprimarygroup"></a>次の項目を取得します。

`CAccessToken`オブジェクトに関連付けられているプライマリ グループを取得します。

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このアクセス トークンが有効な状態で作成されたオブジェクトに対して、グループが既定で設定されます。

## <a name="caccesstokengetprivileges"></a><a name="getprivileges"></a>次の項目を取得します。

`CAccessToken`オブジェクトに関連付けられている特権を取得します。

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>パラメーター

*特権*<br/>
特権を受け取る[CTokenPrivileges クラス](../../atl/reference/ctokenprivileges-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetprocesstoken"></a><a name="getprocesstoken"></a>を使用します。

指定されたプロセスからアクセス トークンを使用して `CAccessToken` を初期化するには、このメソッドを呼び出します。

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*hプロセス*<br/>
アクセス トークンが開いているプロセスへのハンドル。 既定値の NULL を使用すると、現在のプロセスが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

関数を[呼](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken)び出します。

## <a name="caccesstokengetprofile"></a><a name="getprofile"></a>を見る

`CAccessToken`オブジェクトに関連付けられたユーザー プロファイルを指すハンドルを取得します。

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー プロファイルを指すハンドルを返します。

## <a name="caccesstokengetsource"></a><a name="getsource"></a>次の項目を使用します。

`CAccessToken`オブジェクトのソースを取得します。

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>パラメーター

*ソース*<br/>
[TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetstatistics"></a><a name="getstatistics"></a>次の項目を取得します。

オブジェクトに関連付けられた情報を`CAccessToken`取得します。

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>パラメーター

*統計*<br/>
[TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetterminalservicessessionid"></a><a name="getterminalservicessessionid"></a>を指定します。

オブジェクトに関連付けられているターミナル サービス セッション ID`CAccessToken`を取得します。

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
ターミナル サービス セッション ID。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengetthreadtoken"></a><a name="getthreadtoken"></a>を返します。

指定したスレッドのトークンを`CAccessToken`使用して を初期化します。

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>パラメーター

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*hスレッド*<br/>
アクセス トークンが開かれているスレッドへのハンドル。

*自分自身を開く*<br/>
`GetThreadToken`メソッドを呼び出すスレッドのセキュリティ コンテキストに対してアクセス チェックを行うか、呼び出し元のスレッドのプロセスのセキュリティ コンテキストに対してアクセス チェックを行うかを示します。

このパラメーターが FALSE の場合、呼び出し元スレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティ コンテキストはクライアント プロセスのセキュリティ コンテキストにすることができます。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengettokenid"></a><a name="gettokenid"></a>を返します。

`CAccessToken`オブジェクトに関連付けられたトークン ID を取得します。

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*プルイド*<br/>
トークン ID を受け取る[LUID](/windows/win32/api/winnt/ns-winnt-luid)へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokengettype"></a><a name="gettype"></a>次の値を取得します。

`CAccessToken`オブジェクトのトークンの種類を取得します。

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pタイプ*<br/>
成功時にトークンの型を受け取る[TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type)変数のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

TOKEN_TYPE列挙型には、プライマリ トークンと偽装トークンを区別する値が含まれます。

## <a name="caccesstokengetuser"></a><a name="getuser"></a>次の操作を行います。

`CAccessToken`オブジェクトに関連付けられているユーザーを識別します。

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid クラス](../../atl/reference/csid-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="caccesstokenhkeycurrentuser"></a><a name="hkeycurrentuser"></a>キートークン::キーカレントユーザー

`CAccessToken`オブジェクトに関連付けられたユーザー プロファイルを指すハンドルを取得します。

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー プロファイルを指すハンドルを返します。

## <a name="caccesstokenimpersonate"></a><a name="impersonate"></a>偽装

スレッドに偽装`CAccessToken`を割り当てます。

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*hスレッド*<br/>
偽装トークンを割り当てるスレッドへのハンドル。 このハンドルは、TOKEN_IMPERSONATEアクセス権で開かれている必要があります。 *hThread*が NULL の場合、メソッドは、偽装トークンの使用を停止するスレッドを発生させます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、トークンへの有効なポインター`CAccessToken`がない場合、アサーション エラーが発生します。

[クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用して、偽装アクセス トークンを自動的に元に戻すことができます。

## <a name="caccesstokenimpersonateloggedonuser"></a><a name="impersonateloggedonuser"></a>を偽装する

呼び出し元のスレッドがログオンユーザーのセキュリティ コンテキストを偽装できるようにします。

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

> [!IMPORTANT]
> 偽装関数の呼び出しが何らかの理由で失敗した場合、クライアントは偽装されず、クライアント要求は呼び出し元のプロセスのセキュリティ コンテキストで行われます。 プロセスが高い特権を持つアカウントとして実行されている場合、または管理グループのメンバとして実行されている場合、ユーザーは、他の方法で許可されない操作を実行できる可能性があります。 したがって、この関数の戻り値は常に確認する必要があります。

## <a name="caccesstokenistokenrestricted"></a><a name="istokenrestricted"></a>アクセストークン::IsToken制限

オブジェクトに制限付き`CAccessToken`の SID のリストが含まれているかどうかをテストします。

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>戻り値

制限する SID がない場合、またはメソッドが失敗した場合、オブジェクトに制限付きの SID の一覧が含まれている場合は TRUE を返します。

## <a name="caccesstokenloaduserprofile"></a><a name="loaduserprofile"></a>を読み込む

`CAccessToken`オブジェクトに関連付けられているユーザー プロファイルを読み込みます。

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、 に`CAccessToken`有効なトークンが含まれていない場合、またはユーザー プロファイルが既に存在する場合にアサーション エラーが発生します。

## <a name="caccesstokenlogonuser"></a><a name="logonuser"></a>次の操作を行います。

指定された資格情報に関連付けられたユーザーのログオン セッションを作成します。

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
ユーザー名を指定する NULL で終わる文字列へのポインター。 ログオンするユーザー アカウントの名前です。

*ド・スドメイン*<br/>
アカウント データベースに*pszUserName*アカウントが含まれているドメインまたはサーバーの名前を指定する、null で終わる文字列へのポインター。

*パスワード*<br/>
*pszUserName*で指定されたユーザー アカウントのクリア テキスト パスワードを指定する、null で終わる文字列へのポインター。

*ログオンタイプ*<br/>
実行するログオン操作の種類を指定します。 詳細については[、ログオンユーザー](/windows/win32/api/winbase/nf-winbase-logonuserw)を参照してください。

*ドワーログオンプロバイダ*<br/>
ログオン プロバイダーを指定します。 詳細については[、ログオンユーザー](/windows/win32/api/winbase/nf-winbase-logonuserw)を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

ログオンの結果として生成されるアクセス トークンは、`CAccessToken`に関連付けられます。 このメソッドを成功させるには、オブジェクト`CAccessToken`がSE_TCB_NAME特権を保持し、所有者を信頼されたコンピュータ ベースの一部として識別する必要があります。 必要な特権の詳細については[、LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw)を参照してください。

## <a name="caccesstokenopencomclienttoken"></a><a name="opencomclienttoken"></a>をクリックします。

このメソッドは、クライアントからの呼び出しを処理する COM サーバー内`CAccessToken`から呼び出して、COM クライアントからのアクセス トークンを使用して を初期化します。

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*b偽装*<br/>
TRUE の場合、この呼び出しが正常に完了すると、現在のスレッドは呼び出し元の COM クライアントを偽装します。 FALSE の場合、アクセス トークンは開かれますが、この呼び出しが完了すると、スレッドには偽装トークンがありません。

*自分自身を開く*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティ コンテキストに対してアクセス チェックを行うか、呼び出し元のスレッドのプロセスのセキュリティ コンテキストに対してアクセス チェックを行うかを示します。

このパラメーターが FALSE の場合、呼び出し元スレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティ コンテキストはクライアント プロセスのセキュリティ コンテキストにすることができます。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると *、bImpersonate*フラグを TRUE に設定して作成された偽装アクセス トークンを自動的に元に戻すことができます。

## <a name="caccesstokenopennamedpipeclienttoken"></a><a name="opennamedpipeclienttoken"></a>をクリックします。

サーバー内からこのメソッドを呼び出し、名前付きパイプを`CAccessToken`介して要求を受け取って、クライアントからのアクセス トークンを使用して を初期化します。

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*hパイプ*<br/>
名前付きパイプへのハンドル。

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*b偽装*<br/>
TRUE の場合、この呼び出しが正常に完了した場合、現在のスレッドは呼び出しパイプ クライアントを偽装します。 FALSE の場合、アクセス トークンは開かれますが、この呼び出しが完了すると、スレッドには偽装トークンがありません。

*自分自身を開く*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティ コンテキストに対してアクセス チェックを行うか、呼び出し元のスレッドのプロセスのセキュリティ コンテキストに対してアクセス チェックを行うかを示します。

このパラメーターが FALSE の場合、呼び出し元スレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティ コンテキストはクライアント プロセスのセキュリティ コンテキストにすることができます。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると *、bImpersonate*フラグを TRUE に設定して作成された偽装アクセス トークンを自動的に元に戻すことができます。

## <a name="caccesstokenopenrpcclienttoken"></a><a name="openrpcclienttoken"></a>をクリックします。

このメソッドは、RPC クライアントからの呼び出しを処理するサーバー内から`CAccessToken`呼び出して、クライアントからのアクセス トークンを使用して を初期化します。

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*バインディングハンドル*<br/>
クライアントへのバインディングを表すサーバー上のバインディング ハンドル。

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*b偽装*<br/>
TRUE の場合、この呼び出しが正常に完了すると、現在のスレッドは呼び出し元の RPC クライアントを偽装します。 FALSE の場合、アクセス トークンは開かれますが、この呼び出しが完了すると、スレッドには偽装トークンがありません。

*自分自身を開く*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティ コンテキストに対してアクセス チェックを行うか、呼び出し元のスレッドのプロセスのセキュリティ コンテキストに対してアクセス チェックを行うかを示します。

このパラメーターが FALSE の場合、呼び出し元スレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティ コンテキストはクライアント プロセスのセキュリティ コンテキストにすることができます。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックが行われます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると *、bImpersonate*フラグを TRUE に設定して作成された偽装アクセス トークンを自動的に元に戻すことができます。

## <a name="caccesstokenopenthreadtoken"></a><a name="openthreadtoken"></a>をクリックします。

偽装レベルを設定し、指定したスレッドのトークンを`CAccessToken`使用して を初期化します。

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>パラメーター

*アクセスを許可*<br/>
アクセス トークンへの要求されたアクセス タイプを指定するアクセス マスクを指定します。 これらの要求されたアクセス タイプをトークンの DACL と比較することで、どのアクセスを許可するか、または拒否するかを判断します。

*b偽装*<br/>
TRUE の場合、このメソッドが完了した後、スレッドは要求された偽装レベルに残ります。 FALSE の場合、スレッドは元の偽装レベルに戻ります。

*自分自身を開く*<br/>
[GetThreadToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread)メソッドを呼び出すスレッドのセキュリティ コンテキストに対してアクセス チェックを行うか、呼び出し元のスレッドのプロセスのセキュリティ コンテキストに対してアクセス チェックを行うかを示します。

このパラメーターが FALSE の場合、呼び出し元スレッドのセキュリティ コンテキストを使用してアクセス チェックが実行されます。 スレッドがクライアントを偽装している場合、このセキュリティ コンテキストはクライアント プロセスのセキュリティ コンテキストにすることができます。 このパラメーターが TRUE の場合、呼び出し元スレッドのプロセスのセキュリティ コンテキストを使用してアクセス チェックが行われます。

*Sil*<br/>
トークンの偽装レベルを提供する列挙型を[SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level)指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

`OpenThreadToken`は[CAccessToken::GetThreadToken](#getthreadtoken)に似ていますが、スレッドのアクセス トークン`CAccessToken`から初期化する前に偽装レベルを設定します。

[CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用すると *、bImpersonate*フラグを TRUE に設定して作成された偽装アクセス トークンを自動的に元に戻すことができます。

## <a name="caccesstokenprivilegecheck"></a><a name="privilegecheck"></a>:Pリビレゲチェック

オブジェクトで`CAccessToken`指定された特権セットが有効かどうかを調べます。

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>パラメーター

*必要な特権*<br/>
[PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set)構造体へのポインター。

*結果*<br/>
指定された特権のいずれかまたはすべてをオブジェクトで有効にするかどうかを示すために、メソッドが設定する値への`CAccessToken`ポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

戻`PrivilegeCheck`り値が`Attributes`返されると、対応する特権が有効になっている場合、各[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)構造体のメンバーはSE_PRIVILEGE_USED_FOR_ACCESSに設定されます。 このメソッドは[、特権チェック](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck)Win32 関数を呼び出します。

## <a name="caccesstokenrevert"></a><a name="revert"></a>アクセストークン::元に戻す

スレッドが偽装トークンを使用するのを停止します。

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*hスレッド*<br/>
偽装から元に戻すスレッドへのハンドル。 *hThread*が NULL の場合、現在のスレッドが想定されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

偽装トークンの再変換は[、CAutoRevertImpersonation クラス](../../atl/reference/cautorevertimpersonation-class.md)を使用して自動的に実行できます。

## <a name="caccesstokensetdefaultdacl"></a><a name="setdefaultdacl"></a>を設定します。

`CAccessToken`オブジェクトの既定の DACL を設定します。

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>パラメーター

*rDacl*<br/>
新しいデフォルト[の CDacl クラス](../../atl/reference/cdacl-class.md)情報。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

既定の DACL は、このアクセス トークンを有効にして新しいオブジェクトを作成するときに既定で使用される DACL です。

## <a name="caccesstokensetowner"></a><a name="setowner"></a>を指定します。

`CAccessToken`オブジェクトの所有者を設定します。

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
所有者情報を含む[CSid クラス](../../atl/reference/csid-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

所有者は、このアクセス トークンが有効な間に作成された新しいオブジェクトに使用される既定の所有者です。

## <a name="caccesstokensetprimarygroup"></a><a name="setprimarygroup"></a>を設定します。

`CAccessToken`オブジェクトのプライマリ グループを設定します。

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
プライマリ グループ情報を含む[CSid クラス](../../atl/reference/csid-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

プライマリ グループは、このアクセス トークンが有効な状態で作成される新しいオブジェクトの既定のグループです。

## <a name="see-also"></a>関連項目

[ATL セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[アクセストークン](/windows/win32/SecAuthZ/access-tokens)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
