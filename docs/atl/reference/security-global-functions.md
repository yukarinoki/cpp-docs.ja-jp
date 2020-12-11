---
description: '詳細情報: セキュリティグローバル関数'
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
ms.openlocfilehash: 10a3a3f358eba3aa1715bd375221f6ec35a56fcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157790"
---
# <a name="security-global-functions"></a>セキュリティグローバル関数

これらの関数は、SID および ACL オブジェクトの変更をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|名前|説明|
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

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlgetdacl"></a><a name="atlgetdacl"></a> AtlGetDacl

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

*hObject*<br/>
セキュリティ情報を取得する対象のオブジェクトを処理します。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*pDacl*<br/>
取得したセキュリティ情報を格納する DACL オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *Hobject* または *pdacl* が無効な場合にアサーションエラーが発生します。

## <a name="atlsetdacl"></a><a name="atlsetdacl"></a> AtlSetDacl

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

*hObject*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*rDacl*<br/>
新しいセキュリティ情報を含む DACL。

*dwInheritanceFlowControl*<br/>
継承フロー制御。 この値には、0 (既定値)、PROTECTED_DACL_SECURITY_INFORMATION または UNPROTECTED_DACL_SECURITY_INFORMATION を指定できます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *Hobject* が無効な場合、または *dwInheritanceFlowControl* が許可された3つの値のいずれでもない場合に、アサーションエラーが発生します。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlgetgroupsid"></a><a name="atlgetgroupsid"></a> AtlGetGroupSid

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

*hObject*<br/>
セキュリティ情報の取得元となるオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*pSid*<br/>
`CSid`新しいセキュリティ情報を格納するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlsetgroupsid"></a><a name="atlsetgroupsid"></a> AtlSetGroupSid

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

*hObject*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*rSid*<br/>
`CSid`新しいセキュリティ情報を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlgetownersid"></a><a name="atlgetownersid"></a> AtlGetOwnerSid

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

*hObject*<br/>
セキュリティ情報の取得元となるオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*pSid*<br/>
`CSid`新しいセキュリティ情報を格納するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlsetownersid"></a><a name="atlsetownersid"></a> AtlSetOwnerSid

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

*hObject*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*rSid*<br/>
`CSid`新しいセキュリティ情報を格納しているオブジェクト。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlgetsacl"></a><a name="atlgetsacl"></a> AtlGetSacl

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

*hObject*<br/>
セキュリティ情報の取得元となるオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*pSacl*<br/>
取得したセキュリティ情報を格納する SACL オブジェクトへのポインター。

*bRequestNeededPrivileges*<br/>
True の場合、関数は SE_SECURITY_NAME 特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

`AtlGetSacl`が多数の異なるオブジェクトで何度も呼び出される場合は、 *bRequestNeededPrivileges* を false に設定して関数を呼び出す前に、SE_SECURITY_NAME の特権を1回有効にする方が効率的です。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlsetsacl"></a><a name="atlsetsacl"></a> AtlSetSacl

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

*hObject*<br/>
セキュリティ情報を設定するオブジェクトへのハンドル。

*ObjectType*<br/>
*Hobject* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*rSacl*<br/>
新しいセキュリティ情報を含む SACL。

*dwInheritanceFlowControl*<br/>
継承フロー制御。 この値には、0 (既定値)、PROTECTED_SACL_SECURITY_INFORMATION または UNPROTECTED_SACL_SECURITY_INFORMATION を指定できます。

*bRequestNeededPrivileges*<br/>
True の場合、関数は SE_SECURITY_NAME 特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 *Hobject* が無効な場合、または *dwInheritanceFlowControl* が許可された3つの値のいずれでもない場合に、アサーションエラーが発生します。

`AtlSetSacl`が多数の異なるオブジェクトで何度も呼び出される場合は、 *bRequestNeededPrivileges* を false に設定して関数を呼び出す前に、SE_SECURITY_NAME の特権を1回有効にする方が効率的です。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="atlgetsecuritydescriptor"></a><a name="atlgetsecuritydescriptor"></a> AtlGetSecurityDescriptor

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

*pszObjectName*<br/>
セキュリティ情報の取得元となるオブジェクトの名前を指定する、null で終わる文字列へのポインター。

*ObjectType*<br/>
*Pszobjectname* パラメーターによって識別されるオブジェクトの型を示す [SE_OBJECT_TYPE](/windows/win32/api/accctrl/ne-accctrl-se_object_type)列挙からの値を指定します。

*pSecurityDescriptor*<br/>
要求されたセキュリティ記述子を受け取るオブジェクト。

*requestedInfo*<br/>
取得するセキュリティ情報の種類を示す一連の [SECURITY_INFORMATION](/windows/win32/SecAuthZ/security-information) ビットフラグ。 このパラメーターは、次の値の組み合わせにすることができます。

*bRequestNeededPrivileges*<br/>
True の場合、関数は SE_SECURITY_NAME 特権を有効にし、完了時に復元しようとします。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

`AtlGetSecurityDescriptor`が多数の異なるオブジェクトで何度も呼び出される場合は、 *bRequestNeededPrivileges* を false に設定して関数を呼び出す前に、SE_SECURITY_NAME の特権を1回有効にする方が効率的です。

### <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
