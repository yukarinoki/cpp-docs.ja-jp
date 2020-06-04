---
title: セキュリティグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
ms.openlocfilehash: 682d44aa80f5d6de521223dfd67db2813cb6738c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326031"
---
# <a name="security-global-functions"></a>セキュリティグローバル関数

これらの関数は、SID オブジェクトと ACL オブジェクトの変更をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlGetDacl](#atlgetdacl)|指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を取得します。|
|[AtlSetDacl](#atlsetdacl)|指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を設定します。|
|[AtlGetGroupSid](#atlgetgroupsid)|オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を取得します。|
|[AtlSetGroupSid](#atlsetgroupsid)|オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を設定します。|
|[AtlGetOwnerSid](#atlgetownersid)|オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を取得します。|
|[AtlSetOwnerSid](#atlsetownersid)|オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を設定します。|
|[AtlGetSacl](#atlgetsacl)|指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を取得します。|
|[AtlSetSacl](#atlsetsacl)|指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を設定します。|
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|指定されたオブジェクトのセキュリティ記述子を取得します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a>アトルゲダクル

指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を取得します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報を取得する対象のオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*pDacl*<br/>
取得したセキュリティ情報を格納する DACL オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、hObject*または*pDacl*のいずれかが無効な場合にアサーション エラーが発生します。

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a>アトルセットダクル

指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を設定します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*rDacl*<br/>
新しいセキュリティ情報を含む DACL。

*制御の継承*<br/>
継承フロー制御。 この値は、0 (デフォルト)、PROTECTED_DACL_SECURITY_INFORMATION、またはUNPROTECTED_DACL_SECURITY_INFORMATIONにすることができます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、hObject*が無効な場合、または*dwInheritanceFlowControl*が 3 つの許容値の 1 つではない場合、アサーション エラーが発生します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a>アトルゲットグループ

オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を取得します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報の取得元のオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*pSid*<br/>
新しいセキュリティ`CSid`情報を格納するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a>アトルセットグループ

オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を設定します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*rSid*<br/>
新`CSid`しいセキュリティ情報を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a>アトルゲットオーナーズ

オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を取得します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報の取得元のオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*pSid*<br/>
新しいセキュリティ`CSid`情報を格納するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a>アトルセットオーナーズ

オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を設定します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*rSid*<br/>
新`CSid`しいセキュリティ情報を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a>アトルゲットサクル

指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を取得します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報の取得元のオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*pSacl*<br/>
取得したセキュリティ情報を格納する SACL オブジェクトへのポインター。

*必要に応じて特典を受け取る*<br/>
true の場合、関数はSE_SECURITY_NAME特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

多`AtlGetSacl`くの異なるオブジェクトで何度も呼び出される場合は *、bRequestNeededPrivileges*を false に設定して、関数を呼び出す前に SE_SECURITY_NAME 特権を 1 回有効にする方が効率的です。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a>アトルセットサクル

指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を設定します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*オブジェクトタイプ*<br/>
*hObject*パラメーターによって識別されるオブジェクトの種類を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*ルサクル*<br/>
新しいセキュリティ情報を含む SACL。

*制御の継承*<br/>
継承フロー制御。 この値は、0 (デフォルト)、PROTECTED_SACL_SECURITY_INFORMATION、またはUNPROTECTED_SACL_SECURITY_INFORMATIONです。

*必要に応じて特典を受け取る*<br/>
true の場合、関数はSE_SECURITY_NAME特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは *、hObject*が無効な場合、または*dwInheritanceFlowControl*が 3 つの許容値の 1 つではない場合、アサーション エラーが発生します。

多`AtlSetSacl`くの異なるオブジェクトで何度も呼び出される場合は *、bRequestNeededPrivileges*を false に設定して、関数を呼び出す前に SE_SECURITY_NAME 特権を 1 回有効にする方が効率的です。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a>記述子

指定されたオブジェクトのセキュリティ記述子を取得します。

> [!IMPORTANT]
> この関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
bool bRequestNeededPrivileges = true) throw(...);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
セキュリティ情報の取得元のオブジェクトの名前を指定する、NULL で終わる文字列へのポインター。

*オブジェクトタイプ*<br/>
*パラメーター*によって識別されるオブジェクトの型を示す[SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙体の値を指定します。

*記述子*<br/>
要求されたセキュリティ記述子を受け取るオブジェクト。

*要求された情報*<br/>
取得するセキュリティ情報の種類を示す[SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information)ビット フラグのセット。 このパラメーターは、次の値の組み合わせになります。

*必要に応じて特典を受け取る*<br/>
true の場合、関数はSE_SECURITY_NAME特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

多`AtlGetSecurityDescriptor`くの異なるオブジェクトで何度も呼び出される場合は *、bRequestNeededPrivileges*を false に設定して、関数を呼び出す前に SE_SECURITY_NAME 特権を 1 回有効にする方が効率的です。

### <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
