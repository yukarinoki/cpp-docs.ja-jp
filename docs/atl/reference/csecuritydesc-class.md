---
title: CSecurityDesc クラス |Microsoft ドキュメント
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
ms.openlocfilehash: a6963c04e3bd0ba06f8cc2beb9cb77447e2acd81
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366170"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc クラス
このクラスは、用のラッパー、 **SECURITY_DESCRIPTOR**構造体。  
  
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
|[CSecurityDesc::FromString](#fromstring)|有効な機能のセキュリティ記述子の文字列形式のセキュリティ記述子に変換します。|  
|[CSecurityDesc::GetControl](#getcontrol)|取得では、セキュリティ記述子から情報を制御します。|  
|[CSecurityDesc::GetDacl](#getdacl)|セキュリティ記述子から随意アクセス制御リスト (DACL) 情報を取得します。|  
|[CSecurityDesc::GetGroup](#getgroup)|セキュリティ記述子からプライマリ グループの情報を取得します。|  
|[CSecurityDesc::GetOwner](#getowner)|セキュリティ記述子から所有者の情報を取得します。|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|ポインターを返します、 **SECURITY_DESCRIPTOR**構造体。|  
|[CSecurityDesc::GetSacl](#getsacl)|セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL が自動伝達をサポートするために構成されているかどうかを判断します。|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|既定の DACL に設定されているセキュリティ記述子を決定します。|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|セキュリティ記述子に DACL があるかどうかを判断します。|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL が変更を防ぐために構成されているかどうかを判断します。|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されたかどうかを判断します。|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|既定でセキュリティ記述子の所有者の SID が設定されたかどうかを判断します。|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL が自動伝達をサポートするために構成されているかどうかを判断します。|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|既定の SACL のセキュリティ記述子が構成されているかどうかを判断します。|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|セキュリティ記述子に SACL があるかどうかを判断します。|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL が変更を防ぐために構成されているかどうかを判断します。|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|セキュリティ記述子が自己相対形式ではかどうかを判断します。|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::SetControl](#setcontrol)|セキュリティ記述子の制御ビットを設定します。|  
|[CSecurityDesc::SetDacl](#setdacl)|DACL で情報を設定します。 既に DACL が表示されているセキュリティ記述子に置き換えられます。|  
|[CSecurityDesc::SetGroup](#setgroup)|既にあるすべてのプライマリ グループ情報を交換絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。|  
|[CSecurityDesc::SetOwner](#setowner)|所有者の情報がまだ存在して置き換える絶対形式のセキュリティ記述子の所有者の情報を設定します。|  
|[CSecurityDesc::SetSacl](#setsacl)|SACL の情報を設定します。 既に SACL が表示されているセキュリティ記述子に置き換えられます。|  
|[CSecurityDesc::ToString](#tostring)|セキュリティ記述子を文字列形式に変換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|ポインターを返します、 **SECURITY_DESCRIPTOR**構造体。|  
|[CSecurityDesc::operator =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 **SECURITY_DESCRIPTOR**構造体には、オブジェクトに関連付けられているセキュリティ情報が含まれています。 アプリケーションは、設定し、オブジェクトのセキュリティのステータスをクエリにこの構造体を使用します。 関連項目[AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor)です。  
  
 アプリケーションは変更しないでください、 **SECURITY_DESCRIPTOR**構造を直接、代わりにする必要がありますメソッドを使用してクラス提供します。  
  
 Windows でアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)Windows SDK に含まれています。  
  
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
 `rhs`  
 `CSecurityDesc`オブジェクトまたは**SECURITY_DESCRIPTOR**に割り当てる新しい構造`CSecurityDesc`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CSecurityDesc`を使用してオブジェクトを作成することができます必要に応じて、 **SECURITY_DESCRIPTOR**構造体または以前に定義された`CSecurityDesc`オブジェクト。  
  
##  <a name="dtor"></a>  CSecurityDesc:: ~ CSecurityDesc  
 デストラクターです。  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、割り当てられているすべてのリソースを解放します。  
  
##  <a name="fromstring"></a>  CSecurityDesc::FromString  
 有効な機能のセキュリティ記述子の文字列形式のセキュリティ記述子に変換します。  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstr`  
 含む null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379570)変換します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は true を返します。 エラー発生時に例外をスローします。  
  
### <a name="remarks"></a>コメント  
 使用して、文字列を作成することができます[CSecurityDesc::ToString](#tostring)です。 セキュリティ記述子を文字列に変換すると、格納および転送にやすくなります。  
  
 このメソッドを呼び出す[れて](http://msdn.microsoft.com/library/windows/desktop/aa376401)です。  
  
##  <a name="getcontrol"></a>  CSecurityDesc::GetControl  
 取得では、セキュリティ記述子から情報を制御します。  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *psdc*  
 ポインター、 **SECURITY_DESCRIPTOR_CONTROL**セキュリティ記述子の制御情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647)です。  
  
##  <a name="getdacl"></a>  CSecurityDesc::GetDacl  
 セキュリティ記述子から随意アクセス制御リスト (DACL) 情報を取得します。  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDacl`  
 ポインター、`CDacl`セキュリティ記述子の DACL のコピーを格納する構造体。 随意**ACL**メソッドのセットが存在する`pDacl`、アドレスのセキュリティ記述子の随意**ACL**です。 随意**ACL**が存在しない値が格納されません。  
  
 `pbPresent`  
 随意のプレゼンスを示す値を指すポインター **ACL**で指定されたセキュリティ記述子。 セキュリティ記述子が随意が含まれる場合**ACL**、このパラメーターの設定を true にします。 セキュリティ記述子は、随意に含まれない場合**ACL**、このパラメーターが false に設定します。  
  
 `pbDefaulted`  
 フラグへのポインターが SE_DACL_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**随意構造体**ACL**のセキュリティ記述子が存在します。 このフラグが true の場合、随意**ACL** false の場合、既定のメカニズムによって取得された、随意**ACL**ユーザーによって明示的に指定されました。  
  
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
 `pSid`  
 ポインター、 [CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 `pbDefaulted`  
 フラグをポインターであることを示しますフラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**メソッドが戻るときに構造体します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="getowner"></a>  CSecurityDesc::GetOwner  
 セキュリティ記述子から所有者の情報を取得します。  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSid`  
 ポインター、 [CSid](../../atl/reference/csid-class.md) (セキュリティ識別子)、CDacl に格納されているグループのコピーを受信します。  
  
 `pbDefaulted`  
 フラグへのポインターが SE_OWNER_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**メソッドが戻るときに構造体します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 ポインターを返します、 **SECURITY_DESCRIPTOR**構造体。  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)構造体。  
  
##  <a name="getsacl"></a>  CSecurityDesc::GetSacl  
 セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSacl`  
 ポインター、`CSacl`セキュリティ記述子の SACL のコピーを格納する構造体。 システムが、 **ACL**メソッドのセットが存在する`pSacl`セキュリティ記述子のシステムのアドレスに**ACL**です。 システムが、 **ACL**が存在しない値が格納されません。  
  
 `pbPresent`  
 メソッドは、システムの存在を示す設定フラグへのポインター **ACL**で指定されたセキュリティ記述子。 セキュリティ記述子には、システムが含まれている場合**ACL**、このパラメーターの設定を true にします。 セキュリティ記述子には、システムが含まれていない場合**ACL**、このパラメーターが false に設定します。  
  
 `pbDefaulted`  
 フラグへのポインターが SE_SACL_DEFAULTED フラグの値に設定、 **SECURITY_DESCRIPTOR_CONTROL**システムが、構造体**ACL**のセキュリティ記述子が存在します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false が失敗した場合に true を返します。  
  
##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited  
 随意アクセス制御リスト (DACL) が自動伝達をサポートするために構成されているかどうかを判断します。  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトを継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている DACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトと、既存の子オブジェクトに対する自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted  
 既定の随意アクセス制御リスト (DACL) に設定されているセキュリティ記述子を決定します。  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定値の DACL の場合、false それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグは、システムがアクセス制御エントリ (ACE) の継承、DACL を処理する方法に影響することができます。 たとえば、オブジェクトの作成者は、DACL を指定しない場合、オブジェクトは、作成者のアクセス トークンから既定の DACL を受け取ります。 SE_DACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグは、オブジェクトの最終的な DACL を計算する方法を決定するために使用され、セキュリティ保護可能なオブジェクトのセキュリティ記述子のコントロールでは物理的に格納されません。  
  
 このフラグを設定するには、 [csecuritydesc::setdacl](#setdacl)メソッドです。  
  
##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent  
 セキュリティ記述子が随意アクセス制御リスト (DACL) を含むかどうかを判断します。  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、DACL の場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグが設定されていない場合、またはこのフラグが設定されていて、DACL が NULL 場合、セキュリティ記述子は、すべてのユーザーへのフル アクセスを許可します。  
  
 このフラグは、セキュリティ記述子がセキュリティ保護可能なオブジェクトに関連付けされるまで、呼び出し元によって指定されたセキュリティ情報を保持するために使用されます。 セキュリティ記述子は、セキュリティ保護可能なオブジェクトに関連付けられたは、常にセキュリティ記述子制御 SE_DACL_PRESENT フラグが設定されます。  
  
 このフラグを設定するには、 [csecuritydesc::setdacl](#setdacl)メソッドです。  
  
##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected  
 変更を防ぐ随意アクセス制御リスト (DACL) が構成されているかどうかを判断します。  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 DACL をセキュリティ記述子が継承可能なアクセス制御エントリ (Ace) で変更されることを防ぐために構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、 [csecuritydesc::setdacl](#setdacl)メソッドです。  
  
 このメソッドは、継承可能な Ace の自動適用をサポートします。  
  
##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted  
 セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されたかどうかを判断します。  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 True を返しますが、セキュリティ記述子の元のプロバイダーではなく、既定のメカニズムでは、指定のセキュリティ記述子の場合グループ SID。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、 [csecuritydesc::setgroup](#setgroup)メソッドです。  
  
##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted  
 セキュリティ記述子の所有者セキュリティ識別子 (SID) が既定で設定されたかどうかを判断します。  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子の元のプロバイダーではなく、既定のメカニズムは、セキュリティ記述子の所有者の SID を指定した場合は、true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、 [csecuritydesc::setowner](#setowner)メソッドです。  
  
##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited  
 システム アクセス制御リスト (SACL) が自動伝達をサポートするために構成されているかどうかを判断します。  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子には、既存の子オブジェクトを継承可能なアクセス制御エントリ (Ace) の自動適用をサポートするために構成されている SACL が含まれている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトと、既存の子オブジェクトに対する自動的な継承アルゴリズムを実行するときに、このビットが設定されます。  
  
##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted  
 既定のシステム アクセス制御リスト (SACL) に設定されているセキュリティ記述子を決定します。  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、既定の SACL、false それ以外の場合は、true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグは、システムがアクセス制御エントリ (ACE) の継承、SACL を処理する方法に影響することができます。 SE_SACL_PRESENT フラグが設定されていない場合、このフラグは無視されます。  
  
 このフラグを設定するには、 [csecuritydesc::setsacl](#setsacl)メソッドです。  
  
##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent  
 セキュリティ記述子にシステム アクセス制御リスト (SACL) があるかどうかを判断します。  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が含まれる場合、SACL false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、 [csecuritydesc::setsacl](#setsacl)メソッドです。  
  
##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected  
 変更を防ぐシステム アクセス制御リスト (SACL) が構成されているかどうかを判断します。  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 SACL をセキュリティ記述子が継承可能なアクセス制御エントリ (Ace) で変更されることを防ぐために構成されている場合に true を返します。 それ以外の場合は、false を返します。  
  
### <a name="remarks"></a>コメント  
 このフラグを設定するには、 [csecuritydesc::setsacl](#setsacl)メソッドです。  
  
 このメソッドは、継承可能な Ace の自動適用をサポートします。  
  
##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative  
 セキュリティ記述子が自己相対形式ではかどうかを判断します。  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 セキュリティ記述子が自己相対形式で連続するメモリ ブロック内のすべてのセキュリティ情報がある場合は true を返します。 セキュリティ記述子には絶対形式の場合は false を返します。 詳細については、次を参照してください。 [Absolute と Self-Relative セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa374807)です。  
  
##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute  
 セキュリティ記述子を絶対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 絶対形式のセキュリティ記述子には、情報自体ではなく、含まれる情報へのポインターが含まれています。 自己相対形式でセキュリティ記述子には、連続するメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子に、 **SECURITY_DESCRIPTOR**構造は常に、情報を起動しても、セキュリティ記述子の他のコンポーネントが任意の順序での構造に従うことができます。 メモリ アドレスを使用する代わりに、自己相対セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに保存または通信プロトコルを使用して送信される必要がある場合に便利です。 詳細については、次を参照してください。 [Absolute と Self-Relative セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa374807)です。  
  
##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative  
 セキュリティ記述子を自己相対形式に変換するには、このメソッドを呼び出します。  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 絶対形式のセキュリティ記述子には、自体の情報を格納しているのではなく、含まれている情報へのポインターが含まれています。 自己相対形式でセキュリティ記述子には、連続するメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子に、 **SECURITY_DESCRIPTOR**構造は常に、情報を起動しても、セキュリティ記述子の他のコンポーネントが任意の順序での構造に従うことができます。 メモリ アドレスを使用する代わりに、セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに保存または通信プロトコルを使用して送信される必要がある場合に便利です。 詳細については、次を参照してください。 [Absolute と Self-Relative セキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa374807)です。  
  
##  <a name="operator_eq"></a>  CSecurityDesc::operator =  
 代入演算子。  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 **SECURITY_DESCRIPTOR**構造または`CSecurityDesc`オブジェクトに割り当てる、`CSecurityDesc`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CSecurityDesc`オブジェクト。  
  
##  <a name="operator_const_security_descriptor__star"></a>  CSecurityDesc::operator const SECURITY_DESCRIPTOR *  
 ポインターに値をキャスト、 **SECURITY_DESCRIPTOR**構造体。  
  
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
 `ControlBitsOfInterest`  
 A **SECURITY_DESCRIPTOR_CONTROL**マスクを設定する制御ビットを示すです。 設定できるフラグの一覧は、次を参照してください。 [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)です。  
  
 `ControlBitsToSet`  
 `SECURITY_DESCRIPTOR_CONTROL` マスクによって指定される制御ビットの新しい値を示す `ControlBitsOfInterest` マスク。 このパラメーターには、`ControlBitsOfInterest` パラメーターの項に記載されているフラグの組み合わせを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx)です。  
  
##  <a name="setdacl"></a>  CSecurityDesc::SetDacl  
 随意アクセス制御リスト (DACL) で情報を設定します。 既に DACL が表示されているセキュリティ記述子に置き換えられます。  
  
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
 参照、`CDacl`セキュリティ記述子の DACL を指定するオブジェクト。 このパラメーターは NULL をすることはできません。 NULL DACL のセキュリティ記述子を設定するメソッドの最初のフォームで使用する必要があります`bPresent`を false に設定します。  
  
 `bPresent`  
 セキュリティ記述子の DACL が存在するかを示すフラグを指定します。 このパラメーターが true の場合、メソッドには、SE_DACL_PRESENT フラグを設定、 **SECURITY_DESCRIPTOR_CONTROL**構造体の値を使用して、 *Dacl*と`bDefaulted`パラメーター。 False の場合、メソッドは SE_DACL_PRESENT フラグをクリアし、`bDefaulted`は無視されます。  
  
 `bDefaulted`  
 DACL のソースを示すフラグを指定します。 このフラグが true の場合、DACL は既定の機構によって取得されました。 False の場合、DACL がユーザーによって明示的に指定されてです。 メソッドの SE_DACL_DEFAULTED フラグでこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが指定されていない場合、SE_DACL_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 空と存在しない DACL の重要な違いがあります。 DACL が空の場合は、アクセス制御エントリが含まれていないと、アクセス権が明示的に付与されてです。 その結果、オブジェクトへのアクセスが暗黙的に拒否されます。 オブジェクトに DACL がない、その一方で、保護は、オブジェクトに割り当てられませんし、すべてのアクセス要求が許可されます。  
  
##  <a name="setgroup"></a>  CSecurityDesc::SetGroup  
 既にあるすべてのプライマリ グループ情報を交換絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `Sid`  
 参照、 [CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ グループのオブジェクト。 このパラメーターは NULL をすることはできません。 DACL または SACL を持っていないと、セキュリティ記述子が設定されていることができますが、これらも、グループと、所有者必要があります (ある特別な意味を持つ組み込み SID) NULL SID がします。  
  
 `bDefaulted`  
 プライマリ グループの情報が既定のメカニズムから派生したかどうかを示します。 この値は true、それは既定の情報、およびメソッドであることを示しますフラグとしてこの値を格納する場合、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが 0 の場合、SE_GROUP_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setowner"></a>  CSecurityDesc::SetOwner  
 絶対形式のセキュリティ記述子の所有者の情報を設定します。 所有者の情報がまだ存在してが置き換えられます。  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `Sid`  
 [CSid](../../atl/reference/csid-class.md)セキュリティ記述子の新しいプライマリ所有者のオブジェクト。 このパラメーターは NULL をすることはできません。  
  
 `bDefaulted`  
 所有者の情報が既定のメカニズムから派生したかどうかを示します。 この値が true の場合は、既定の情報です。 メソッドで SE_OWNER_DEFAULTED フラグとしてこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが 0 の場合、SE_OWNER_DEFAULTED フラグがクリアされます。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
##  <a name="setsacl"></a>  CSecurityDesc::SetSacl  
 システム アクセス制御リスト (SACL) の情報を設定します。 既に SACL が表示されているセキュリティ記述子に置き換えられます。  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *Sacl*  
 ポインター、`CSacl`のセキュリティ記述子の SACL を指定するオブジェクト。 このパラメーターは NULL をすることはできません、CSacl オブジェクトである必要があります。 Dacl とは異なりは NULL と空の SACL の違い SACL オブジェクトのみの監査情報のアクセス権を指定しないとします。  
  
 `bDefaulted`  
 SACL のソースを示すフラグを指定します。 このフラグが true の場合、SACL は既定の機構によって取得されました。 False の場合、SACL がユーザーによって明示的に指定されてです。 メソッドの SE_SACL_DEFAULTED フラグでこの値を格納する、 **SECURITY_DESCRIPTOR_CONTROL**構造体。 このパラメーターが指定されていない場合、SE_SACL_DEFAULTED フラグがクリアされます。  
  
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
 `pstr`  
 受け取る null で終わる文字列へのポインター、[文字列形式のセキュリティ記述子](http://msdn.microsoft.com/library/windows/desktop/aa379570)です。  
  
 `si`  
 出力文字列に含めるセキュリティ記述子のコンポーネントを示すために SECURITY_INFORMATION ビット フラグの組み合わせを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 セキュリティ記述子は、文字列の形式より簡単には、格納されているまたは送信します。 使用して、`CSecurityDesc::FromString`セキュリティ記述子に、文字列に変換します。  
  
 `si`パラメーターは、次の SECURITY_INFORMATION フラグを含めることができます。  
  
|[値]|説明|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|所有者を含めます。|  
|GROUP_SECURITY_INFORMATION|プライマリ グループを含めます。|  
|DACL_SECURITY_INFORMATION|DACL が含まれます。|  
|SACL_SECURITY_INFORMATION|SACL が含まれます。|  
  
 DACL が NULL、SE_DACL_PRESENT 制御ビットを設定、入力セキュリティ記述子の場合、メソッドが失敗します。  
  
 DACL が NULL の入力セキュリティ記述子内 SE_DACL_PRESENT 制御ビットが設定されていない場合は、結果として得られるセキュリティ記述子文字列には d: コンポーネントはありません。 参照してください[セキュリティ記述子の文字列形式](http://msdn.microsoft.com/library/windows/desktop/aa379570)詳細についてはします。  
  
 このメソッドを呼び出す[れて](http://msdn.microsoft.com/library/windows/desktop/aa376401)です。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
