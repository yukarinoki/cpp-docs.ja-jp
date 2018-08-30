---
title: CSecurityDesc クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea4bfc278e0912248c437123bd1510002a5c3829
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201628"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc クラス
このクラスは、のラッパー、`SECURITY_DESCRIPTOR`構造体。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|コンストラクターです。|  
|[CSecurityDesc:: ~ CSecurityDesc](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|文字列形式のセキュリティ記述子を有効な機能のセキュリティ記述子に変換します。|  
|[CSecurityDesc::GetControl](#getcontrol)|セキュリティ記述子から情報を制御するを取得します。|  
|[CSecurityDesc::GetDacl](#getdacl)|セキュリティ記述子の随意アクセス制御リスト (DACL) の情報を取得します。|  
|[CSecurityDesc::GetGroup](#getgroup)|セキュリティ記述子からプライマリ グループの情報を取得します。|  
|[CSecurityDesc::GetOwner](#getowner)|セキュリティ記述子の所有者の情報を取得します。|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|ポインターを返します、`SECURITY_DESCRIPTOR`構造体。|  
|[CSecurityDesc::GetSacl](#getsacl)|セキュリティ記述子からシステム アクセス制御リスト (SACL) の情報を取得します。|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL が自動伝達をサポートするために構成されているかどうかを決定します。|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|既定の DACL に設定されているセキュリティ記述子を決定します。|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|セキュリティ記述子に DACL があるかどうかを決定します。|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|変更を防ぐために、DACL が構成されているかどうかを決定します。|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されたかどうかを決定します。|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|既定では、セキュリティ記述子の所有者の SID が設定されたかどうかを決定します。|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL が自動伝達をサポートするために構成されているかどうかを決定します。|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|既定の SACL に設定されているセキュリティ記述子を決定します。|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|セキュリティ記述子に SACL があるかどうかを決定します。|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|変更を防ぐ、SACL が構成されているかどうかを決定します。|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|セキュリティ記述子が自己相対形式のかどうかを判断します。|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::SetControl](#setcontrol)|セキュリティ記述子の制御ビットを設定します。|  
|[CSecurityDesc::SetDacl](#setdacl)|DACL で情報を設定します。 DACL が既にセキュリティ記述子に存在する場合は置き換えられます。|  
|[CSecurityDesc::SetGroup](#setgroup)|既に存在するプライマリ グループの情報を置き換える絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。|  
|[CSecurityDesc::SetOwner](#setowner)|所有者の情報が既に存在するを置き換える絶対形式のセキュリティ記述子の所有者の情報を設定します。|  
|[CSecurityDesc::SetSacl](#setsacl)|SACL で情報を設定します。 SACL が既にセキュリティ記述子に存在する場合は置き換えられます。|  
|[CSecurityDesc::ToString](#tostring)|セキュリティ記述子を文字列形式に変換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|ポインターを返します、`SECURITY_DESCRIPTOR`構造体。|  
|[CSecurityDesc::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>Remarks  
 `SECURITY_DESCRIPTOR`構造体には、オブジェクトに関連付けられているセキュリティ情報が含まれています。 アプリケーションでは、オブジェクトのセキュリティ状態の照会や設定をこの構造体を使用します。 参照してください[AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor)します。  
  
 アプリケーションは変更しないでください、`SECURITY_DESCRIPTOR`構造直接必要がありますを使用して、クラスのメソッドを提供します。  
  
 Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="csecuritydesc"></a>  CSecurityDesc::CSecurityDesc  
 コンストラクターです。  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *rhs*  
 `CSecurityDesc`オブジェクトまたは`SECURITY_DESCRIPTOR`構造に割り当てる新しい`CSecurityDesc`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CSecurityDesc`を使用してオブジェクトを作成することができます必要に応じて、`SECURITY_DESCRIPTOR`構造体または以前に定義された`CSecurityDesc`オブジェクト。  
  
##  <a name="dtor"></a>  CSecurityDesc:: ~ CSecurityDesc  
 デストラクターです。  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Remarks  
 デストラクターは、割り当てられているすべてのリソースを解放します。  
  
##  <a name="fromstring"></a>  CSecurityDesc::FromString  
 文字列形式のセキュリティ記述子を有効な機能のセキュリティ記述子に変換します。  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstr*  
 含む null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](/windows/desktop/SecAuthZ/security-descriptor-string-format)に変換します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に true を返します。 エラー発生時に、例外をスローします。  
  
### <a name="remarks"></a>Remarks  
 使用して、文字列を作成できる[CSecurityDesc::ToString](#tostring)します。 セキュリティ記述子を文字列に変換すると、格納および転送するやすくなります。  
  
 このメソッドを呼び出す[convertstringsecuritydescriptortosecuritydescriptor が](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)します。  
  
##  <a name="getcontrol"></a>  CSecurityDesc::GetControl  
 セキュリティ記述子から情報を制御するを取得します。  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *psdc*  
 ポインター、`SECURITY_DESCRIPTOR_CONTROL`セキュリティ記述子の制御情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す[GetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa446647)します。  
  
##  <a name="getdacl"></a>  CSecurityDesc::GetDacl  
 セキュリティ記述子の随意アクセス制御リスト (DACL) の情報を取得します。  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDacl*  
 ポインター、`CDacl`セキュリティ記述子の DACL のコピーを格納する構造体。 随意 ACL が存在する場合、メソッドは設定*pDacl*セキュリティ記述子の随意 ACL のアドレスにします。 随意 ACL が存在しない場合、値は格納されません。  
  
 *pbPresent*  
 指定したセキュリティ記述子の随意 ACL のプレゼンスを示す値を指すポインター。 このパラメーターを設定する場合は、セキュリティ記述子には、随意 ACL が含まれている、true に設定します。 セキュリティ記述子に随意 ACL が含まれていない場合は、このパラメーターが false に設定されます。  
  
 *pbDefaulted*  
 SE_DACL_DEFAULTED フラグの値にフラグへのポインターの設定、`SECURITY_DESCRIPTOR_CONTROL`のセキュリティ記述子の随意 ACL が存在する場合に構造体します。 随意 ACL が既定の機構によって取得されたこのフラグが true の場合false の場合、随意 ACL がユーザーによって明示的に指定します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="getgroup"></a>  CSecurityDesc::GetGroup  
 セキュリティ記述子からプライマリ グループの情報を取得します。  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSid*  
 ポインターを[CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 *pbDefaulted*  
 フラグをポインターであることを示しますフラグの値に設定、`SECURITY_DESCRIPTOR_CONTROL`メソッドが戻るときに構造体します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="getowner"></a>  CSecurityDesc::GetOwner  
 セキュリティ記述子の所有者の情報を取得します。  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSid*  
 ポインターを[CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 *pbDefaulted*  
 SE_OWNER_DEFAULTED フラグの値にフラグへのポインターの設定、`SECURITY_DESCRIPTOR_CONTROL`メソッドが戻るときに構造体します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 ポインターを返します、`SECURITY_DESCRIPTOR`構造体。  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)構造体。  
  
##  <a name="getsacl"></a>  CSecurityDesc::GetSacl  
 セキュリティ記述子からシステム アクセス制御リスト (SACL) の情報を取得します。  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *psacl の値として*  
 ポインター、`CSacl`セキュリティ記述子の SACL のコピーを格納する構造体。 システムの ACL が存在する場合、メソッドを設定*psacl の値として*セキュリティ記述子のシステム ACL のアドレスにします。 システムの ACL が存在しない場合、値は格納されません。  
  
 *pbPresent*  
 指定したセキュリティ記述子にシステム ACL の存在を示すフラグ、メソッドへのポインターを設定します。 セキュリティ記述子にシステム ACL が含まれている場合は、このパラメーターが設定を true にします。 セキュリティ記述子にシステム ACL が含まれていない場合は、このパラメーターが false に設定されます。  
  
 *pbDefaulted*  
 SE_SACL_DEFAULTED フラグの値にフラグへのポインターの設定、`SECURITY_DESCRIPTOR_CONTROL`のセキュリティ記述子のシステムの ACL が存在する場合に構造体します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited  
 随意アクセス制御リスト (DACL) が自動伝達をサポートするために構成されているかどうかを決定します。  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトに継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている DACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 オブジェクトとその既存の子オブジェクトの自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted  
 既定の随意アクセス制御リスト (DACL) に設定されているセキュリティ記述子を決定します。  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定の DACL の場合、false それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグは、システムがアクセス制御エントリ (ACE) の継承に関して、DACL を処理する方法に影響します。 たとえば、オブジェクトの作成者は、DACL を指定しない場合、オブジェクトは、作成者のアクセス トークンから既定の DACL を受け取ります。 SE_DACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグは、オブジェクトの最終的な DACL の計算方法を決定するために使用され、セキュリティ保護可能なオブジェクトのセキュリティ記述子のコントロールに物理的に格納されていません。  
  
 このフラグを設定するには、使用、 [csecuritydesc::setdacl](#setdacl)メソッド。  
  
##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent  
 セキュリティ記述子が随意アクセス制御リスト (DACL) を含むかどうかを決定します。  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、DACL の場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグが設定されていない場合、またはこのフラグが設定され、DACL が NULL の場合、セキュリティ記述子は、すべてのユーザーへのフル アクセスを許可します。  
  
 このフラグは、セキュリティ記述子にはセキュリティ保護可能なオブジェクトに関連付けられたまで、呼び出し元によって指定されたセキュリティ情報を保持するために使用されます。 セキュリティ記述子は、セキュリティ保護可能なオブジェクトに関連付けられたが、常にセキュリティ記述子制御 SE_DACL_PRESENT フラグが設定されます。  
  
 このフラグを設定するには、使用、 [csecuritydesc::setdacl](#setdacl)メソッド。  
  
##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected  
 随意アクセス制御リスト (DACL) が変更を防ぐために構成されているかどうかを決定します。  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が継承可能なアクセス制御エントリ (Ace) によって変更されることを防ぐために、DACL が構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグを設定するには、使用、 [csecuritydesc::setdacl](#setdacl)メソッド。  
  
 このメソッドは、ace の継承可能な自動伝達をサポートします。  
  
##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted  
 セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されたかどうかを決定します。  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 True を返しますが、セキュリティ記述子の元のプロバイダーではなく、既定の機構はセキュリティ記述子の指定されている場合グループ SID。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグを設定するには、使用、 [csecuritydesc::setgroup](#setgroup)メソッド。  
  
##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted  
 セキュリティ記述子の所有者セキュリティ識別子 (SID) が既定で設定されたかどうかを決定します。  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子の元のプロバイダーではなく、既定の機構にセキュリティ記述子の所有者の SID が指定されている場合は、true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグを設定するには、使用、 [csecuritydesc::setowner](#setowner)メソッド。  
  
##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited  
 システム アクセス制御リスト (SACL) が自動伝達をサポートするために構成されているかどうかを決定します。  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトに継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている SACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 オブジェクトとその既存の子オブジェクトの自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted  
 既定のシステム アクセス制御リスト (SACL) に設定されているセキュリティ記述子を決定します。  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定値、SACL false それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグは、アクセス制御エントリ (ACE) の継承に関して、SACL の処理方法に影響します。 SE_SACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグを設定するには、使用、 [csecuritydesc::setsacl](#setsacl)メソッド。  
  
##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent  
 セキュリティ記述子にシステム アクセス制御リスト (SACL) があるかどうかを決定します。  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、SACL false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグを設定するには、使用、 [csecuritydesc::setsacl](#setsacl)メソッド。  
  
##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected  
 変更を防ぐシステム アクセス制御リスト (SACL) が構成されているかどうかを決定します。  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が継承可能なアクセス制御エントリ (Ace) によって変更されることを防ぐために、SACL が構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグを設定するには、使用、 [csecuritydesc::setsacl](#setsacl)メソッド。  
  
 このメソッドは、ace の継承可能な自動伝達をサポートします。  
  
##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative  
 セキュリティ記述子が自己相対形式のかどうかを判断します。  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が自己相対形式で連続するメモリ ブロック内のすべてのセキュリティ情報がある場合に true を返します。 セキュリティ記述子には絶対形式の場合は false を返します。 詳細については、次を参照してください。[絶対有効期限と Self-Relative セキュリティ記述子](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)します。  
  
##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute  
 セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>Remarks  
 絶対形式のセキュリティ記述子には、情報自体ではなく、含まれる情報へのポインターが含まれています。 自己相対形式のセキュリティ記述子には、連続するメモリ ブロックの情報が含まれています。 自己相対のセキュリティ記述子で、`SECURITY_DESCRIPTOR`構造体は、情報を常に開始されますが、セキュリティ記述子の他のコンポーネントは任意の順序で構造に従うことができます。 メモリ アドレスを使用する代わりに、自己相対のセキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに格納されているまたは通信プロトコルを使用して送信する必要がある場合に便利です。 詳細については、次を参照してください。[絶対有効期限と Self-Relative セキュリティ記述子](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)します。  
  
##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative  
 セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>Remarks  
 絶対形式のセキュリティ記述子には、自体の情報を格納しているのではなく、それに含まれる情報へのポインターが含まれています。 自己相対形式のセキュリティ記述子には、連続するメモリ ブロックの情報が含まれています。 自己相対のセキュリティ記述子で、`SECURITY_DESCRIPTOR`構造体は、情報を常に開始されますが、セキュリティ記述子の他のコンポーネントは任意の順序で構造に従うことができます。 メモリ アドレスを使用する代わりに、セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに格納されているまたは通信プロトコルを使用して送信する必要がある場合に便利です。 詳細については、次を参照してください。[絶対有効期限と Self-Relative セキュリティ記述子](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)します。  
  
##  <a name="operator_eq"></a>  CSecurityDesc::operator =  
 代入演算子。  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *rhs*  
 `SECURITY_DESCRIPTOR`構造または`CSecurityDesc`オブジェクトに割り当てる、`CSecurityDesc`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された返します`CSecurityDesc`オブジェクト。  
  
##  <a name="operator_const_security_descriptor__star"></a>  CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 値へのポインターにキャスト、`SECURITY_DESCRIPTOR`構造体。  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="setcontrol"></a>  CSecurityDesc::SetControl  
 セキュリティ記述子の制御ビットを設定します。  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *ControlBitsOfInterest*  
 設定する制御ビットを示す SECURITY_DESCRIPTOR_CONTROL マスク。 設定できるフラグの一覧は、次を参照してください。 [SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)します。  
  
 *ControlBitsToSet*  
 によって指定される制御ビットの新しい値を示す SECURITY_DESCRIPTOR_CONTROL マスク、 *ControlBitsOfInterest*マスク。 このパラメーターの一覧表示フラグの組み合わせを指定できます、 *ControlBitsOfInterest*パラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す[SetSecurityDescriptorControl](https://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)します。  
  
##  <a name="setdacl"></a>  CSecurityDesc::SetDacl  
 随意アクセス制御リスト (DACL) で情報を設定します。 DACL が既にセキュリティ記述子に存在する場合は置き換えられます。  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *Dacl*  
 参照を`CDacl`のセキュリティ記述子の DACL を指定するオブジェクト。 このパラメーターには、NULL は指定できません。 NULL DACL のセキュリティ記述子を設定すると、メソッドの最初のフォームを使用する必要があります*bPresent*を false に設定します。  
  
 *bPresent*  
 セキュリティ記述子の DACL の存在を示すフラグを指定します。 このパラメーターが true の場合、メソッド SE_DACL_PRESENT フラグを設定、`SECURITY_DESCRIPTOR_CONTROL`構造体の値を使用して、 *Dacl*と*bDefaulted*パラメーター。 メソッドが、SE_DACL_PRESENT フラグをクリアが false の場合と*bDefaulted*は無視されます。  
  
 *bDefaulted*  
 DACL のソースを示すフラグを指定します。 このフラグが true の場合、DACL が既定の機構によって取得されました。 False の場合のユーザーによって DACL を明示的に指定されています。 メソッドの SE_DACL_DEFAULTED フラグでこの値を格納する、`SECURITY_DESCRIPTOR_CONTROL`構造体。 このパラメーターが指定されていない場合、SE_DACL_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 空と存在しない DACL の重要な違いがあります。 DACL が空の場合は、アクセス制御エントリを含んでいないと、アクセス権が明示的に付与されていません。 その結果、オブジェクトへのアクセスは暗黙的に拒否されます。 その一方で、オブジェクトに DACL があるないときは、保護は、オブジェクトに割り当てられませんし、アクセス要求が許可されます。  
  
##  <a name="setgroup"></a>  CSecurityDesc::SetGroup  
 既に存在するプライマリ グループの情報を置き換える絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *sid*  
 参照を[CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ グループのオブジェクト。 このパラメーターには、NULL は指定できません。 DACL または SACL がなくなると、セキュリティ記述子を設定できますが、グループと所有者は、これらもありますが NULL の SID (される特別な意味を持つ組み込みの SID)。  
  
 *bDefaulted*  
 プライマリ グループの情報が既定のメカニズムから派生したかどうかを示します。 この値は true、既定の情報、およびメソッドであることを示しますフラグとしてこの値を格納する場合、`SECURITY_DESCRIPTOR_CONTROL`構造体。 このパラメーターが 0 の場合、SE_GROUP_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setowner"></a>  CSecurityDesc::SetOwner  
 絶対形式のセキュリティ記述子の所有者の情報を設定します。 所有者の情報が既に存在するが置き換えられます。  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *sid*  
 [CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ所有者のオブジェクト。 このパラメーターには、NULL は指定できません。  
  
 *bDefaulted*  
 所有者情報が既定の機構から派生したかどうかを示します。 この値が true の場合は、既定の情報です。 メソッドで SE_OWNER_DEFAULTED フラグとしてこの値を格納する、`SECURITY_DESCRIPTOR_CONTROL`構造体。 このパラメーターが 0 の場合、SE_OWNER_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setsacl"></a>  CSecurityDesc::SetSacl  
 システム アクセス制御リスト (SACL) の情報を設定します。 SACL が既にセキュリティ記述子に存在する場合は置き換えられます。  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *Sacl*  
 ポインター、`CSacl`のセキュリティ記述子の SACL を指定するオブジェクト。 このパラメーターは NULL をすることはできません、CSacl オブジェクトである必要があります。 Dacl とは異なり違いはありません NULL と、空の SACL のオブジェクトの SACL は監査のみの情報のアクセス権を指定していないようです。  
  
 *bDefaulted*  
 SACL のソースを示すフラグを指定します。 このフラグが true の場合、SACL が既定の機構によって取得されました。 False の場合、ユーザーによって SACL を明示的に指定されています。 メソッドの SE_SACL_DEFAULTED フラグでこの値を格納する、`SECURITY_DESCRIPTOR_CONTROL`構造体。 このパラメーターが指定されていない場合、SE_SACL_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="tostring"></a>  CSecurityDesc::ToString  
 セキュリティ記述子を文字列形式に変換します。  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstr*  
 受信する null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](/windows/desktop/SecAuthZ/security-descriptor-string-format)します。  
  
 *si*  
 出力文字列に含めるセキュリティ記述子のコンポーネントを示す SECURITY_INFORMATION ビット フラグの組み合わせを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>Remarks  
 セキュリティ記述子は、文字列の形式より簡単には、格納されているまたは送信します。 使用して、`CSecurityDesc::FromString`文字列をセキュリティ記述子に変換するメソッド。  
  
 *Si*パラメーターは、次の SECURITY_INFORMATION フラグを含めることができます。  
  
|[値]|説明|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|所有者を含めます。|  
|GROUP_SECURITY_INFORMATION|プライマリ グループが含まれます。|  
|DACL_SECURITY_INFORMATION|DACL が含まれます。|  
|SACL_SECURITY_INFORMATION|SACL が含まれます。|  
  
 DACL が NULL、入力のセキュリティ記述子で SE_DACL_PRESENT の制御ビットが設定されている場合は、メソッドは失敗します。  
  
 DACL が NULL で、入力のセキュリティ記述子で SE_DACL_PRESENT の制御ビットが設定されていない、結果として得られるセキュリティ記述子文字列には d: コンポーネントはありません。 参照してください[セキュリティ記述子の文字列形式](/windows/desktop/SecAuthZ/security-descriptor-string-format)の詳細。  
  
 このメソッドを呼び出す[convertstringsecuritydescriptortosecuritydescriptor が](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)します。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
