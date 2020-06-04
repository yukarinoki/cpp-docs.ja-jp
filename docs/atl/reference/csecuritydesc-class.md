---
title: クラスをセキュリティします。
ms.date: 11/04/2016
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
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: 926e4e0a795982479188d90ed866bf5e2584c187
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330971"
---
# <a name="csecuritydesc-class"></a>クラスをセキュリティします。

このクラスは構造体のラッパー`SECURITY_DESCRIPTOR`です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CSecurityDesc
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[セキュリティデスク::セキュリティデスク](#csecuritydesc)|コンストラクターです。|
|[セキュリティデスク::~セキュリティーデック](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[セキュリティデスク::文字列から](#fromstring)|文字列形式のセキュリティ記述子を有効な機能セキュリティ記述子に変換します。|
|[セキュリティデック::ゲットコントロール](#getcontrol)|セキュリティ記述子からコントロール情報を取得します。|
|[セキュリティデスク::ゲットダクル](#getdacl)|セキュリティ記述子から随意アクセス制御リスト (DACL) 情報を取得します。|
|[セキュリティデスク::ゲットグループ](#getgroup)|セキュリティ記述子からプライマリ グループ情報を取得します。|
|[セキュリティデスク::取得所有者](#getowner)|セキュリティ記述子から所有者の情報を取得します。|
|[セキュリティデスク::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|構造体へのポインターを`SECURITY_DESCRIPTOR`返します。|
|[セキュリティデスク::ゲットサクル](#getsacl)|セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。|
|[Cセキュリティデスク::IsDaclオートコント継承](#isdaclautoinherited)|DACL が自動伝達をサポートするように構成されているかどうかを判断します。|
|[セキュリティディスク::IsDaclデフォルト](#isdacldefaulted)|セキュリティ記述子が既定の DACL で構成されているかどうかを判断します。|
|[セキュリティデスク::IsDaclプレゼント](#isdaclpresent)|セキュリティ記述子に DACL が含まれているかどうかを判断します。|
|[セキュリティディスク::IsDaclProtected](#isdaclprotected)|DACL が変更を防ぐために構成されているかどうかを判断します。|
|[セキュリティディスク::IsGroupデフォルト](#isgroupdefaulted)|セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されているかどうかを判断します。|
|[セキュリティディスク::IsOwner デフォルト](#isownerdefaulted)|セキュリティ記述子の所有者 SID が既定で設定されているかどうかを確認します。|
|[Cセキュリティデスク::IsSaclオートコント継承](#issaclautoinherited)|SACL が自動伝達をサポートするように構成されているかどうかを判断します。|
|[セキュリティディスク::イサクルデフォルト](#issacldefaulted)|セキュリティ記述子が既定の SACL で構成されているかどうかを判断します。|
|[セキュリティデスク::イサクルプレゼント](#issaclpresent)|セキュリティ記述子に SACL が含まれているかどうかを判断します。|
|[セキュリティディスク::イサクラフド](#issaclprotected)|変更を防ぐために SACL が構成されているかどうかを判断します。|
|[セキュリティディスク::イズセルフアカレント](#isselfrelative)|セキュリティ記述子が自己相対形式かどうかを判断します。|
|[セキュリティデスク::メイクアブソリュート](#makeabsolute)|セキュリティ記述子を絶対形式に変換します。|
|[セキュリティデスク::自己相対性](#makeselfrelative)|セキュリティ記述子を自己相対形式に変換します。|
|[セキュリティデスク::セットコントロール](#setcontrol)|セキュリティ記述子の制御ビットを設定します。|
|[セキュリティデスク::セットダクル](#setdacl)|DACL に情報を設定します。 DACL がセキュリティ記述子に既に存在する場合は、置き換えられます。|
|[セキュリティデスク::セットグループ](#setgroup)|絶対形式セキュリティ記述子のプライマリ グループ情報を設定し、既に存在しているプライマリ グループ情報を置き換えます。|
|[セキュリティデスク::セットオーナー](#setowner)|既に存在する所有者情報を置き換えて、絶対形式のセキュリティ記述子の所有者情報を設定します。|
|[セキュリティデスク::セットサクル](#setsacl)|SACL に情報を設定します。 SACL がセキュリティ記述子に既に存在する場合は、置き換えられます。|
|[セキュリティデスク::トストリング](#tostring)|セキュリティ記述子を文字列形式に変換します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[cSecurityDesc::演算子の定数SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|構造体へのポインターを`SECURITY_DESCRIPTOR`返します。|
|[セキュリティデスク::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

構造体`SECURITY_DESCRIPTOR`には、オブジェクトに関連付けられたセキュリティ情報が含まれます。 アプリケーションは、この構造を使用して、オブジェクトのセキュリティステータスを設定し、照会します。 「[セキュリティ記述子」](security-global-functions.md#atlgetsecuritydescriptor)も参照してください。

アプリケーションは、構造体を`SECURITY_DESCRIPTOR`直接変更するのではなく、提供されたクラス メソッドを使用する必要があります。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>セキュリティデスク::セキュリティデスク

コンストラクターです。

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
新`CSecurityDesc`しい`CSecurityDesc`オブジェクト`SECURITY_DESCRIPTOR`に割り当てるオブジェクトまたは構造体。

### <a name="remarks"></a>解説

オブジェクト`CSecurityDesc`は、必要に応じて、構造体`SECURITY_DESCRIPTOR`または定義済みの`CSecurityDesc`オブジェクトを使用して作成できます。

## <a name="csecuritydesccsecuritydesc"></a><a name="dtor"></a>セキュリティデスク::~セキュリティーデック

デストラクターです。

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>解説

デストラクタは、割り当てられたすべてのリソースを解放します。

## <a name="csecuritydescfromstring"></a><a name="fromstring"></a>セキュリティデスク::文字列から

文字列形式のセキュリティ記述子を有効な機能セキュリティ記述子に変換します。

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>パラメーター

*プストル*<br/>
変換する[文字列形式のセキュリティ記述子](/windows/win32/SecAuthZ/security-descriptor-string-format)を含む null で終わる文字列へのポインター。

### <a name="return-value"></a>戻り値

成功時に true を返します。 失敗時に例外をスローします。

### <a name="remarks"></a>解説

文字列は[、CSecurityDesc::ToString](#tostring)を使用して作成できます。 セキュリティ記述子を文字列に変換すると、格納と転送が容易になります。

このメソッドは、記述子を呼び出[します。](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)

## <a name="csecuritydescgetcontrol"></a><a name="getcontrol"></a>セキュリティデック::ゲットコントロール

セキュリティ記述子からコントロール情報を取得します。

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>パラメーター

*psdc*<br/>
セキュリティ記述子の`SECURITY_DESCRIPTOR_CONTROL`コントロール情報を受け取る構造体へのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、失敗した場合は false を返します。

### <a name="remarks"></a>解説

このメソッド[は、を](/windows/win32/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)呼び出します。

## <a name="csecuritydescgetdacl"></a><a name="getdacl"></a>セキュリティデスク::ゲットダクル

セキュリティ記述子から随意アクセス制御リスト (DACL) 情報を取得します。

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pDacl*<br/>
セキュリティ記述子の`CDacl`DACL のコピーを格納する構造体へのポインター。 随意 ACL が存在する場合、メソッドは *、pDacl*をセキュリティ記述子の随意 ACL のアドレスに設定します。 任意の ACL が存在しない場合、値は保存されません。

*pbプレゼント*<br/>
指定されたセキュリティ記述子に随意 ACL が存在することを示す値へのポインター。 セキュリティ記述子に随意 ACL が含まれている場合、このパラメーターは true に設定されます。 セキュリティ記述子に随意 ACL が含まれていない場合、このパラメーターは false に設定されます。

*pbデフォルト*<br/>
セキュリティ記述子に対して任意の ACL が存在する場合`SECURITY_DESCRIPTOR_CONTROL`、構造体のSE_DACL_DEFAULTED フラグの値に設定されたフラグへのポインター。 このフラグが true の場合、随意 ACL はデフォルトのメカニズムによって取得されました。false の場合、任意の ACL はユーザーによって明示的に指定されました。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、失敗した場合は false を返します。

## <a name="csecuritydescgetgroup"></a><a name="getgroup"></a>セキュリティデスク::ゲットグループ

セキュリティ記述子からプライマリ グループ情報を取得します。

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
CDacl に格納されているグループのコピーを受け取る[CSid](../../atl/reference/csid-class.md) (セキュリティ識別子) へのポインタ。

*pbデフォルト*<br/>
メソッドが返されるときに構造体のSE_GROUP_DEFAULTED フラグの値に設定された`SECURITY_DESCRIPTOR_CONTROL`フラグへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、失敗した場合は false を返します。

## <a name="csecuritydescgetowner"></a><a name="getowner"></a>セキュリティデスク::取得所有者

セキュリティ記述子から所有者の情報を取得します。

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
CDacl に格納されているグループのコピーを受け取る[CSid](../../atl/reference/csid-class.md) (セキュリティ識別子) へのポインタ。

*pbデフォルト*<br/>
メソッドが返されるときに、構造体のSE_OWNER_DEFAULTED フラグの値に`SECURITY_DESCRIPTOR_CONTROL`設定されたフラグへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、失敗した場合は false を返します。

## <a name="csecuritydescgetpsecurity_descriptor"></a><a name="getpsecurity_descriptor"></a>セキュリティデスク::GetPSECURITY_DESCRIPTOR

構造体へのポインターを`SECURITY_DESCRIPTOR`返します。

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>戻り値

[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)構造体へのポインターを返します。

## <a name="csecuritydescgetsacl"></a><a name="getsacl"></a>セキュリティデスク::ゲットサクル

セキュリティ記述子からシステム アクセス制御リスト (SACL) 情報を取得します。

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSacl*<br/>
セキュリティ記述子の`CSacl`SACL のコピーを格納する構造体へのポインター。 システム ACL が存在する場合、メソッドは *、pSacl*をセキュリティ記述子のシステム ACL のアドレスに設定します。 システム ACL が存在しない場合、値は保存されません。

*pbプレゼント*<br/>
指定されたセキュリティ記述子にシステム ACL が存在することを示すために、メソッドセットのフラグへのポインター。 セキュリティ記述子にシステム ACL が含まれている場合、このパラメーターは true に設定されます。 セキュリティ記述子にシステム ACL が含まれていない場合、このパラメータは false に設定されます。

*pbデフォルト*<br/>
セキュリティ記述子に対してシステム ACL が存在する場合、`SECURITY_DESCRIPTOR_CONTROL`構造体のSE_SACL_DEFAULTED フラグの値に設定されたフラグへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、失敗した場合は false を返します。

## <a name="csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>Cセキュリティデスク::IsDaclオートコント継承

自動伝播をサポートするように随意アクセス制御リスト (DACL) が構成されているかどうかを判断します。

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>戻り値

既存の子オブジェクトへの継承可能なアクセス制御エントリ (ACE) の自動伝達をサポートするように設定された DACL がセキュリティ記述子に含まれている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

システムは、オブジェクトとその既存の子オブジェクトに対して自動継承アルゴリズムを実行するときに、このビットを設定します。

## <a name="csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>セキュリティディスク::IsDaclデフォルト

セキュリティ記述子が既定の随意アクセス制御リスト (DACL) で構成されているかどうかを判断します。

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子に既定の DACL が含まれている場合は true を返します。

### <a name="remarks"></a>解説

このフラグは、アクセス制御エントリ (ACE) 継承に関して、システムが DACL を処理する方法に影響を与える可能性があります。 たとえば、オブジェクトの作成者が DACL を指定しない場合、オブジェクトは作成者のアクセス トークンから既定の DACL を受け取ります。 SE_DACL_PRESENT フラグが設定されていない場合、システムはこのフラグを無視します。

このフラグは、オブジェクトの最終的な DACL を計算する方法を決定するために使用され、セキュリティ保護可能なオブジェクトのセキュリティ記述子コントロールに物理的に格納されません。

このフラグを設定するには[、CSecurityDesc::SetDacl](#setdacl)メソッドを使用します。

## <a name="csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>セキュリティデスク::IsDaclプレゼント

セキュリティ記述子に随意アクセス制御リスト (DACL) が含まれているかどうかを判断します。

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子に DACL が含まれている場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

このフラグが設定されていない場合、またはこのフラグが設定され、DACL が NULL の場合、セキュリティ記述子は、すべてのユーザーにフル アクセスを許可します。

このフラグは、セキュリティ記述子がセキュリティ保護可能なオブジェクトに関連付けられるまで、呼び出し元によって指定されたセキュリティ情報を保持するために使用されます。 セキュリティ記述子がセキュリティ保護可能なオブジェクトに関連付けられると、SE_DACL_PRESENT フラグは常にセキュリティ記述子コントロールに設定されます。

このフラグを設定するには[、CSecurityDesc::SetDacl](#setdacl)メソッドを使用します。

## <a name="csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>セキュリティディスク::IsDaclProtected

随意アクセス制御リスト (DACL) が変更を防ぐように構成されているかどうかを判断します。

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>戻り値

DACL が、継承可能なアクセス制御エントリ (ACE) によってセキュリティ記述子が変更されないように構成されている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

このフラグを設定するには[、CSecurityDesc::SetDacl](#setdacl)メソッドを使用します。

この方法は、継承可能な ACE の自動伝播をサポートします。

## <a name="csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>セキュリティディスク::IsGroupデフォルト

セキュリティ記述子のグループ セキュリティ識別子 (SID) が既定で設定されているかどうかを判断します。

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子のグループ SID が指定された既定の機構 (セキュリティ記述子の元のプロバイダーではなく) が指定されている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

このフラグを設定するには[、CSecurityDesc::SetGroup](#setgroup)メソッドを使用します。

## <a name="csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>セキュリティディスク::IsOwner デフォルト

セキュリティ記述子の所有者セキュリティ識別子 (SID) が既定で設定されているかどうかを判断します。

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子の所有者 SID が指定された既定の機構 (セキュリティ記述子の元のプロバイダーではなく) が指定されている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

このフラグを設定するには[、CSecurityDesc::SetOwner](#setowner)メソッドを使用します。

## <a name="csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>Cセキュリティデスク::IsSaclオートコント継承

システム アクセス制御リスト (SACL) が自動伝播をサポートするように構成されているかどうかを判断します。

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>戻り値

既存の子オブジェクトへの継承可能なアクセス制御エントリ (ACE) の自動伝達をサポートするように設定された SACL がセキュリティ記述子に含まれている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

システムは、オブジェクトとその既存の子オブジェクトに対して自動継承アルゴリズムを実行するときに、このビットを設定します。

## <a name="csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>セキュリティディスク::イサクルデフォルト

セキュリティ記述子が既定のシステム アクセス制御リスト (SACL) で構成されているかどうかを判断します。

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子に既定の SACL が含まれている場合は true を返します。

### <a name="remarks"></a>解説

このフラグは、アクセス制御エントリ (ACE) 継承に関して、システムが SACL を処理する方法に影響を与える可能性があります。 SE_SACL_PRESENTフラグが設定されていない場合、システムはこのフラグを無視します。

このフラグを設定するには[、CSecurityDesc::SetSacl](#setsacl)メソッドを使用します。

## <a name="csecuritydescissaclpresent"></a><a name="issaclpresent"></a>セキュリティデスク::イサクルプレゼント

セキュリティ記述子にシステム アクセス制御リスト (SACL) が含まれているかどうかを判断します。

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子に SACL が含まれている場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

このフラグを設定するには[、CSecurityDesc::SetSacl](#setsacl)メソッドを使用します。

## <a name="csecuritydescissaclprotected"></a><a name="issaclprotected"></a>セキュリティディスク::イサクラフド

システム アクセス制御リスト (SACL) が変更されないように構成されているかどうかを判断します。

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子が継承可能なアクセス制御エントリ (ACE) によって変更されないように SACL が構成されている場合は true を返します。 それ以外の場合は、false を返します。

### <a name="remarks"></a>解説

このフラグを設定するには[、CSecurityDesc::SetSacl](#setsacl)メソッドを使用します。

この方法は、継承可能な ACE の自動伝播をサポートします。

## <a name="csecuritydescisselfrelative"></a><a name="isselfrelative"></a>セキュリティディスク::イズセルフアカレント

セキュリティ記述子が自己相対形式かどうかを判断します。

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>戻り値

セキュリティ記述子が自己相対形式で、連続するすべてのセキュリティ情報が連続したメモリ ブロックにある場合は true を返します。 セキュリティ記述子が絶対形式の場合は false を返します。 詳細については、「[絶対セキュリティ記述子と自己相対セキュリティ記述子](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)」を参照してください。

## <a name="csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>セキュリティデスク::メイクアブソリュート

セキュリティ記述子を絶対形式に変換します。

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

絶対形式のセキュリティ記述子には、情報自体ではなく、含まれている情報へのポインターが含まれています。 自己相対形式のセキュリティ記述子には、連続したメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子では、`SECURITY_DESCRIPTOR`構造体は常に情報を開始しますが、セキュリティ記述子の他のコンポーネントは、任意の順序で構造体に従うことができます。 自己相対セキュリティ記述子のコンポーネントは、メモリ アドレスを使用する代わりに、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに格納する必要がある場合や、通信プロトコルを使用して送信する必要がある場合に便利です。 詳細については、「[絶対セキュリティ記述子と自己相対セキュリティ記述子](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)」を参照してください。

## <a name="csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>セキュリティデスク::自己相対性

セキュリティ記述子を自己相対形式に変換します。

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

絶対形式のセキュリティ記述子には、情報自体を含むのではなく、含まれている情報へのポインターが含まれます。 自己相対形式のセキュリティ記述子には、連続したメモリ ブロック内の情報が含まれています。 自己相対セキュリティ記述子では、`SECURITY_DESCRIPTOR`構造体は常に情報を開始しますが、セキュリティ記述子の他のコンポーネントは、任意の順序で構造体に従うことができます。 メモリ アドレスを使用する代わりに、セキュリティ記述子のコンポーネントは、セキュリティ記述子の先頭からのオフセットによって識別されます。 この形式は、セキュリティ記述子をディスクに格納する必要がある場合や、通信プロトコルを使用して送信する必要がある場合に便利です。 詳細については、「[絶対セキュリティ記述子と自己相対セキュリティ記述子](/windows/win32/SecAuthZ/absolute-and-self-relative-security-descriptors)」を参照してください。

## <a name="csecuritydescoperator-"></a><a name="operator_eq"></a>セキュリティデスク::演算子 =

代入演算子。

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
オブジェクトに割`CSecurityDesc`り当てる構造体またはオブジェクト。 `SECURITY_DESCRIPTOR` `CSecurityDesc`

### <a name="return-value"></a>戻り値

更新された`CSecurityDesc`オブジェクトを返します。

## <a name="csecuritydescoperator-const-security_descriptor-"></a><a name="operator_const_security_descriptor__star"></a>cSecurityDesc::演算子の定数SECURITY_DESCRIPTOR *

構造体へのポインターに値をキャストします`SECURITY_DESCRIPTOR`。

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

## <a name="csecuritydescsetcontrol"></a><a name="setcontrol"></a>セキュリティデスク::セットコントロール

セキュリティ記述子の制御ビットを設定します。

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>パラメーター

*興味を持つ*<br/>
設定する制御ビットを示す SECURITY_DESCRIPTOR_CONTROL マスク。 設定できるフラグの一覧については、「[セキュリティ記述子コントロールの設定](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)」を参照してください。

*セット*<br/>
*controlBitsOfinterest*マスクで指定されたコントロール ビットの新しい値を示すSECURITY_DESCRIPTOR_CONTROLマスク。 このパラメーターは、*パラメーター*に示されているフラグの組み合わせにすることができます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

このメソッド[は、コントロールを](/windows/win32/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)呼び出します。

## <a name="csecuritydescsetdacl"></a><a name="setdacl"></a>セキュリティデスク::セットダクル

随意アクセス制御リスト (DACL) の情報を設定します。 DACL がセキュリティ記述子に既に存在する場合は、置き換えられます。

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*Dacl*<br/>
セキュリティ記述子の`CDacl`DACL を指定するオブジェクトへの参照。 このパラメーターは NULL にすることはできません。 セキュリティ記述子に NULL DACL を設定するには、メソッドの最初の形式を使用して *、bPresent*を false に設定します。

*bプレゼント*<br/>
セキュリティ記述子に DACL が存在するフラグを指定します。 このパラメーターが true の場合、メソッドは構造体にSE_DACL_PRESENT`SECURITY_DESCRIPTOR_CONTROL`フラグを設定し *、Dacl*および*bDefaulted*パラメーターの値を使用します。 false の場合、メソッドはSE_DACL_PRESENT フラグをクリアし *、bDefaulted*は無視されます。

*bデフォルト*<br/>
DACL のソースを示すフラグを指定します。 このフラグが true の場合、DACL は既定のメカニズムによって取得されています。 false の場合、DACL はユーザーによって明示的に指定されています。 このメソッドは、この値を構造体のSE_DACL_DEFAULTED`SECURITY_DESCRIPTOR_CONTROL`フラグに格納します。 このパラメーターを指定しない場合、SE_DACL_DEFAULTED フラグはクリアされます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

空の DACL と存在しない DACL には重要な違いがあります。 DACL が空の場合、アクセス制御エントリは含まれず、アクセス権は明示的に付与されていません。 その結果、オブジェクトへのアクセスは暗黙的に拒否されます。 一方、オブジェクトに DACL がない場合は、オブジェクトに保護が割り当てられていないし、アクセス要求も許可されます。

## <a name="csecuritydescsetgroup"></a><a name="setgroup"></a>セキュリティデスク::セットグループ

絶対形式セキュリティ記述子のプライマリ グループ情報を設定し、既に存在しているプライマリ グループ情報を置き換えます。

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*Sid*<br/>
セキュリティ記述子の新しいプライマリ グループの[CSid](../../atl/reference/csid-class.md)オブジェクトへの参照。 このパラメーターは NULL にすることはできません。 セキュリティ記述子は、DACL または SACL を持たないとマークできますが、グループと所有者が必要です。

*bデフォルト*<br/>
プライマリ グループ情報が既定のメカニズムから派生したかどうかを示します。 この値が true の場合、この情報は既定の情報であり、メソッドはこの値をSE_GROUP_DEFAULTEDフラグ`SECURITY_DESCRIPTOR_CONTROL`として構造体に格納します。 このパラメーターがゼロの場合、SE_GROUP_DEFAULTED フラグはクリアされます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

## <a name="csecuritydescsetowner"></a><a name="setowner"></a>セキュリティデスク::セットオーナー

絶対形式セキュリティ記述子の所有者情報を設定します。 既に存在している所有者情報は置き換えられます。

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*Sid*<br/>
セキュリティ記述子の新しいプライマリ所有者の[CSid](../../atl/reference/csid-class.md)オブジェクト。 このパラメーターは NULL にすることはできません。

*bデフォルト*<br/>
所有者情報が既定の機構から派生するかどうかを示します。 この値が true の場合は、デフォルト情報になります。 このメソッドは、この値を構造体のSE_OWNER_DEFAULTEDフラグ`SECURITY_DESCRIPTOR_CONTROL`として格納します。 このパラメーターがゼロの場合、SE_OWNER_DEFAULTED フラグはクリアされます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

## <a name="csecuritydescsetsacl"></a><a name="setsacl"></a>セキュリティデスク::セットサクル

システム アクセス制御リスト (SACL) の情報を設定します。 SACL がセキュリティ記述子に既に存在する場合は、置き換えられます。

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*Sacl*<br/>
セキュリティ記述子の`CSacl`SACL を指定するオブジェクトへのポインター。 このパラメーターは NULL であってはならず、CSacl オブジェクトでなければなりません。 DACL とは異なり、SACL オブジェクトはアクセス権を指定せず、監査情報のみを指定するので、NULL と空の SACL の間に違いはありません。

*bデフォルト*<br/>
SACL のソースを示すフラグを指定します。 このフラグが true の場合、SACL は既定のメカニズムによって取得されています。 false の場合、SACL はユーザーによって明示的に指定されています。 このメソッドは、構造体のSE_SACL_DEFAULTED フラグにこの`SECURITY_DESCRIPTOR_CONTROL`値を格納します。 このパラメーターを指定しない場合は、SE_SACL_DEFAULTED フラグがクリアされます。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

## <a name="csecuritydesctostring"></a><a name="tostring"></a>セキュリティデスク::トストリング

セキュリティ記述子を文字列形式に変換します。

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>パラメーター

*プストル*<br/>
[文字列形式のセキュリティ記述子](/windows/win32/SecAuthZ/security-descriptor-string-format)を受け取る null で終わる文字列へのポインター。

*Si*<br/>
出力文字列に含めるセキュリティ記述子のコンポーネントを示すビット フラグSECURITY_INFORMATION組み合わせて指定します。

### <a name="return-value"></a>戻り値

正常に終了した場合は true を返します。失敗した場合は false を返します。

### <a name="remarks"></a>解説

セキュリティ記述子を文字列形式にすると、より簡単に格納または転送できます。 このメソッド`CSecurityDesc::FromString`を使用して、文字列をセキュリティ記述子に変換します。

*si*パラメーターには、次のSECURITY_INFORMATIONフラグを含めることができます。

|[値]|意味|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|所有者を含めます。|
|GROUP_SECURITY_INFORMATION|プライマリ グループを含めます。|
|DACL_SECURITY_INFORMATION|DACL を含めます。|
|SACL_SECURITY_INFORMATION|SACL を含めます。|

DACL が NULL で、SE_DACL_PRESENTコントロール ビットが入力セキュリティ記述子に設定されている場合、メソッドは失敗します。

DACL が NULL で、SE_DACL_PRESENTコントロール ビットが入力セキュリティ記述子に設定されていない場合、結果のセキュリティ記述子文字列には D: コンポーネントがありません。 詳細については、「[セキュリティ記述子の文字列形式](/windows/win32/SecAuthZ/security-descriptor-string-format)」を参照してください。

このメソッドは、記述子を呼び出[します。](/windows/win32/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptorw)

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
