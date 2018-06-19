---
title: セキュリティのグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9ad170706b72c9d236e095db0e2b6df00031ff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365055"
---
# <a name="security-global-functions"></a>セキュリティのグローバル関数
これらの関数は、オブジェクトの SID と ACL オブジェクトを変更するためのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
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

## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlgetdacl"></a>  AtlGetDacl  
 指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を取得します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `pDacl`  
 取得したセキュリティ情報を含む DACL オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生する場合`hObject`または`pDacl`が無効です。  
  
##  <a name="atlsetdacl"></a>  AtlSetDacl  
 指定されたオブジェクトの随意アクセス制御リスト (DACL: Discretionary Access Control List) の情報を設定します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `rDacl`  
 新しいセキュリティ情報を含む DACL です。  
  
 `dwInheritanceFlowControl`  
 継承のフロー制御します。 この値は、0 (既定)、PROTECTED_DACL_SECURITY_INFORMATION または UNPROTECTED_DACL_SECURITY_INFORMATION を指定できます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`hObject`が有効でない場合、または`dwInheritanceFlowControl`3 つの許容値のいずれかではありません。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlgetgroupsid"></a>  AtlGetGroupSid  
 オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を取得します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `pSid`  
 ポインター、`CSid`新しいセキュリティ情報を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlsetgroupsid"></a>  AtlSetGroupSid  
 オブジェクトのグループ セキュリティ識別子 (SID: Security Identifier) を設定します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `rSid`  
 `CSid`新しいセキュリティ情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlgetownersid"></a>  AtlGetOwnerSid  
 オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を取得します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `pSid`  
 ポインター、`CSid`新しいセキュリティ情報を格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlsetownersid"></a>  AtlSetOwnerSid  
 オブジェクトの所有者セキュリティ識別子 (SID: Security Identifier) を設定します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `rSid`  
 `CSid`新しいセキュリティ情報を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlgetsacl"></a>  AtlGetSacl  
 指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を取得します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 `pSacl`  
 取得したセキュリティ情報を含む SACL オブジェクトへのポインター。  
  
 `bRequestNeededPrivileges`  
 True の場合、関数は SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合`AtlGetSacl`多数の異なるオブジェクトに何度も呼び出すは効率的で、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にすることが`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlsetsacl"></a>  AtlSetSacl  
 指定されたオブジェクトのシステム アクセス制御リスト (SACL: System Access Control List) の情報を設定します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、`hObject`パラメーター。  
  
 *rSacl*  
 新しいセキュリティ情報を含む SACL です。  
  
 `dwInheritanceFlowControl`  
 継承のフロー制御します。 この値は、0 (既定)、PROTECTED_SACL_SECURITY_INFORMATION または UNPROTECTED_SACL_SECURITY_INFORMATION を指定できます。  
  
 `bRequestNeededPrivileges`  
 True の場合、関数は SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合はデバッグ ビルドで、アサーション エラーが発生`hObject`が有効でない場合、または`dwInheritanceFlowControl`3 つの許容値のいずれかではありません。  
  
 場合`AtlSetSacl`多数の異なるオブジェクトに何度も呼び出すは効率的で、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にすることが`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 

##  <a name="atlgetsecuritydescriptor"></a>  AtlGetSecurityDescriptor  
 指定されたオブジェクトのセキュリティ記述子を取得します。  
  
> [!IMPORTANT]
>  この関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
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
 *pszObjectName*  
 セキュリティ情報を取得する対象のオブジェクトの名前を指定する null で終わる文字列へのポインター。  
  
 `ObjectType`  
 値を指定して、 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593)列挙体によって識別されるオブジェクトの種類を示す、 *pszObjectName*パラメーター。  
  
 *pSecurityDescriptor*  
 要求されたセキュリティ記述子を受信するオブジェクト。  
  
 *requestedInfo*  
 一連の[SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)ビットを取得するセキュリティ情報の種類を示すフラグ。 このパラメーターは、次の値の組み合わせを指定できます。  
  
 `bRequestNeededPrivileges`  
 True の場合、関数は SE_SECURITY_NAME 特権を有効にして、完了時に復元を試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 場合`AtlGetSecurityDescriptor`多数の異なるオブジェクトに何度も呼び出すは効率的で、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にすることが`bRequestNeededPrivileges`を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
