---
title: セキュリティに関するグローバル関数 |Microsoft Docs
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
ms.openlocfilehash: 053e7adb5a0f5d6c65f599ae694525853bd221a7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211792"
---
# <a name="security-global-functions"></a>セキュリティに関するグローバル関数
これらの関数は、オブジェクトの SID と ACL を変更するためのサポートを提供します。  
  
> [!IMPORTANT]
>  Windows ランタイムで実行するアプリケーションでは、次の表に示す関数を使用できません。  
  
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
 *hObject*  
 セキュリティ情報を取得する対象のオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *pDacl*  
 取得したセキュリティ情報を含む DACL オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 どちらの場合、デバッグ ビルドで、アサーション エラーが発生*hObject*または*pDacl*が無効です。  
  
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
 *hObject*  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *rDacl*  
 新しいセキュリティ情報を含む DACL。  
  
 *dwInheritanceFlowControl*  
 継承のフロー制御します。 この値は 0 (既定)、PROTECTED_DACL_SECURITY_INFORMATION または UNPROTECTED_DACL_SECURITY_INFORMATION を指定できます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 場合、デバッグ ビルドで、アサーション エラーが発生*hObject*が有効でない場合、または*dwInheritanceFlowControl*許可されている 3 つの値ではありません。  
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
 *hObject*  
 セキュリティ情報の取得元となるオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *pSid*  
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
 *hObject*  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *rSid*  
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
 *hObject*  
 セキュリティ情報の取得元となるオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *pSid*  
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
 *hObject*  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *rSid*  
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
 *hObject*  
 セキュリティ情報の取得元となるオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *psacl の値として*  
 取得したセキュリティ情報を含む SACL のオブジェクトへのポインター。  
  
 *bRequestNeededPrivileges*  
 True の場合、関数が SE_SECURITY_NAME 特権には、有効にして、完了時に復元することを試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 場合`AtlGetSacl`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります*bRequestNeededPrivileges*を false に設定します。  

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
 *hObject*  
 セキュリティ情報を設定する対象のオブジェクトへのハンドルします。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *hObject*パラメーター。  
  
 *rSacl*  
 新しいセキュリティ情報を格納している SACL。  
  
 *dwInheritanceFlowControl*  
 継承のフロー制御します。 この値は 0 (既定)、PROTECTED_SACL_SECURITY_INFORMATION または UNPROTECTED_SACL_SECURITY_INFORMATION を指定できます。  
  
 *bRequestNeededPrivileges*  
 True の場合、関数が SE_SECURITY_NAME 特権には、有効にして、完了時に復元することを試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 場合、デバッグ ビルドで、アサーション エラーが発生*hObject*が有効でない場合、または*dwInheritanceFlowControl*許可されている 3 つの値ではありません。  
  
 場合`AtlSetSacl`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります*bRequestNeededPrivileges*を false に設定します。  

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
 セキュリティ情報の取得元となるオブジェクトの名前を指定する null で終わる文字列へのポインター。  
  
 *ObjectType*  
 値を指定します、 [SE_OBJECT_TYPE](/windows/desktop/api/accctrl/ne-accctrl-_se_object_type)で識別されるオブジェクトの種類を示す列挙体、 *pszObjectName*パラメーター。  
  
 *pSecurityDescriptor*  
 要求されたセキュリティ記述子を受け取るオブジェクト。  
  
 *requestedInfo*  
 一連の[SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information)ビットを取得するセキュリティ情報の種類を示すフラグ。 このパラメーターは、次の値の組み合わせを指定できます。  
  
 *bRequestNeededPrivileges*  
 True の場合、関数が SE_SECURITY_NAME 特権には、有効にして、完了時に復元することを試みます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 場合`AtlGetSecurityDescriptor`が何度もを多数の異なるオブジェクトで呼び出されると、関数を呼び出す前に 1 回 SE_SECURITY_NAME 特権を有効にする方が効率的になります*bRequestNeededPrivileges*を false に設定します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h 
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
