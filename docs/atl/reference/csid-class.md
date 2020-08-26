---
title: CSid クラス
ms.date: 03/27/2019
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: b6787c0e3f075935f19d51aa73bbd66da9cc0fcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835598"
---
# <a name="csid-class"></a>CSid クラス

このクラスは、 `SID` (セキュリティ識別子) 構造体のラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CSid
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CSid:: CSidArray](#csidarray)|`CSid` オブジェクトの配列。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSid:: CSid](#csid)|コンストラクターです。|
|[CSid:: ~ CSid](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSid:: AccountName](#accountname)|オブジェクトに関連付けられているアカウントの名前を返し `CSid` ます。|
|[CSid::D omain](#domain)|オブジェクトに関連付けられているドメインの名前を返し `CSid` ます。|
|[CSid:: EqualPrefix](#equalprefix)|テスト `SID` (セキュリティ識別子) が等しいかどうかのプレフィックス。|
|[CSid:: GetLength](#getlength)|オブジェクトの長さを返し `CSid` ます。|
|[CSid:: GetPSID](#getpsid)|構造体へのポインターを返し `SID` ます。|
|[CSid:: GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|構造体へのポインターを返し `SID_IDENTIFIER_AUTHORITY` ます。|
|[CSid:: GetSubAuthority](#getsubauthority)|構造体の指定された subauthority を返し `SID` ます。|
|[CSid:: GetSubAuthorityCount](#getsubauthoritycount)|Subauthority の数を返します。|
|[CSid:: IsValid](#isvalid)|オブジェクトの `CSid` 有効性をテストします。|
|[CSid:: LoadAccount](#loadaccount)|`CSid`アカウント名とドメイン、または既存の構造体を指定して、オブジェクトを更新し `SID` ます。|
|[CSid:: Sid](#sid)|ID 文字列を返します。|
|[CSid:: SidNameUse](#sidnameuse)|オブジェクトの状態の説明を返し `CSid` ます。|

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator =](#operator_eq)|代入演算子。|
|[operator const SID *](#operator_const_sid__star)|オブジェクトを `CSid` 構造体へのポインターにキャスト `SID` します。|

### <a name="global-operators"></a>グローバル演算子

|名前|説明|
|-|-|
|[operator = =](#operator_eq_eq)|2つのセキュリティ記述子オブジェクトが等しいかどうかをテストします|
|[operator! =](#operator_neq)|2つのセキュリティ記述子オブジェクトが等しくないかどうかをテストします|
|[operator \<](#operator_lt)|2つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[>演算子 ](#operator_gt)|2つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[operator \<=](#operator_lt__eq)|2つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[operator >=](#operator_gt__eq)|2つのセキュリティ記述子オブジェクトの相対値を比較します。|

## <a name="remarks"></a>解説

構造は、 `SID` ユーザーまたはグループを一意に識別するために使用される可変長構造です。

アプリケーションは構造を直接変更しないでください `SID` 。代わりに、このラッパークラスに用意されているメソッドを使用してください。 「 [AtlGetOwnerSid](security-global-functions.md#atlgetownersid)、 [atlsetgroupsid](security-global-functions.md#atlsetgroupsid)、 [atlsetgroupsid](security-global-functions.md#atlgetgroupsid)、および [AtlSetOwnerSid](security-global-functions.md#atlsetownersid)」も参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity .h

## <a name="csidaccountname"></a><a name="accountname"></a> CSid:: AccountName

オブジェクトに関連付けられているアカウントの名前を返し `CSid` ます。

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>戻り値

アカウントの名前を指す LPCTSTR を返します。

### <a name="remarks"></a>解説

このメソッドは、指定された (セキュリティ識別子) の名前の検索を試み `SID` ます。 詳細については、「 [lookupaccountsid 関数](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)」を参照してください。

のアカウント名が見つからない場合 `SID` 、は空の文字列を `AccountName` 返します。 これは、ネットワークのタイムアウトによって、このメソッドによって名前が検索されない場合に発生する可能性があります。 また、 `SID` サインインセッションを識別するなど、対応するアカウント名のないセキュリティ識別子に対しても発生します。

## <a name="csidcsid"></a><a name="csid"></a> CSid:: CSid

コンストラクターです。

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存 `CSid` のオブジェクトまたは `SID` (セキュリティ識別子) 構造体。

*IdentifierAuthority*<br/>
権限。

*nSubAuthorityCount*<br/>
Subauthority の数。

*pszAccountName*<br/>
アカウント名。

*pszSystem*<br/>
システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。

*pSid*<br/>
構造体へのポインター `SID` 。

### <a name="remarks"></a>解説

コンストラクターは、オブジェクトを初期化し `CSid` 、内部データメンバーを *Sidtypeinvalid*に設定するか、既存 `CSid` の、 `SID` 、または既存のアカウントから設定をコピーします。

初期化に失敗した場合、コンストラクターは [CAtlException クラス](../../atl/reference/catlexception-class.md)をスローします。

## <a name="csidcsid"></a><a name="dtor"></a> CSid:: ~ CSid

デストラクターです。

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>解説

デストラクターは、オブジェクトによって取得されたすべてのリソースを解放します。

## <a name="csidcsidarray"></a><a name="csidarray"></a> CSid:: CSidArray

[CSid](../../atl/reference/csid-class.md)オブジェクトの配列。

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>解説

この typedef は、ACL (アクセス制御リスト) からセキュリティ識別子を取得するために使用できる配列型を指定します。 「 [CAcl:: GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)」を参照してください。

## <a name="csiddomain"></a><a name="domain"></a> CSid::D omain

オブジェクトに関連付けられているドメインの名前を返し `CSid` ます。

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>戻り値

`LPCTSTR`ドメインを指すを返します。

### <a name="remarks"></a>解説

このメソッドは、指定された (セキュリティ識別子) の名前の検索を試み `SID` ます。 詳細については、「 [lookupaccountsid 関数](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)」を参照してください。

のアカウント名が見つからない場合は `SID` 、 `Domain` ドメインを空の文字列として返します。 これは、ネットワークのタイムアウトによって、このメソッドによって名前が検索されない場合に発生する可能性があります。 また、 `SID` サインインセッションを識別するなど、対応するアカウント名のないセキュリティ識別子に対しても発生します。

## <a name="csidequalprefix"></a><a name="equalprefix"></a> CSid:: EqualPrefix

テスト `SID` (セキュリティ識別子) が等しいかどうかのプレフィックス。

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`SID`比較する (セキュリティ識別子) 構造体または `CSid` オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の「 [EqualPrefixSid](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) 」を参照してください。

## <a name="csidgetlength"></a><a name="getlength"></a> CSid:: GetLength

オブジェクトの長さを返し `CSid` ます。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの長さをバイト単位で返し `CSid` ます。

### <a name="remarks"></a>解説

`CSid`構造体が有効でない場合、戻り値は未定義になります。 を呼び出す前に `GetLength` 、 [CSid:: IsValid](#isvalid) メンバー関数を使用して、が有効であることを確認し `CSid` ます。

> [!NOTE]
> デバッグビルドでは、 `CSid` オブジェクトが有効でない場合、関数によってアサートが発生します。

## <a name="csidgetpsid"></a><a name="getpsid"></a> CSid:: GetPSID

`SID`(セキュリティ識別子) 構造体へのポインターを返します。

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>戻り値

`CSid`オブジェクトの基になる構造体のアドレスを返し `SID` ます。

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a> CSid:: GetPSID_IDENTIFIER_AUTHORITY

構造体へのポインターを返し `SID_IDENTIFIER_AUTHORITY` ます。

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、構造体のアドレスを返し `SID_IDENTIFIER_AUTHORITY` ます。 失敗した場合、戻り値は未定義になります。 オブジェクトが有効でない場合、エラーが発生する可能性があります。この場合、 `CSid` [CSid:: IsValid](#isvalid) メソッドは FALSE を返します。 関数は、 `GetLastError` 拡張されたエラー情報に対して呼び出すことができます。

> [!NOTE]
> デバッグビルドでは、 `CSid` オブジェクトが有効でない場合、関数によってアサートが発生します。

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a> CSid:: GetSubAuthority

(セキュリティ識別子) 構造体で指定された subauthority を返し `SID` ます。

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>パラメーター

*nSubAuthority*<br/>
Subauthority。

### <a name="return-value"></a>戻り値

NSubAuthority によって参照される subauthority を返し *ます。* Subauthority 値は相対識別子 (RID) です。

### <a name="remarks"></a>解説

*NSubAuthority*パラメーターは、メソッドが返す subauthority array 要素を識別するインデックス値を指定します。 メソッドは、この値に対して検証テストを実行しません。 アプリケーションは、 [CSid:: GetSubAuthorityCount](#getsubauthoritycount) を呼び出して、許容される値の範囲を見つけることができます。

> [!NOTE]
> デバッグビルドでは、 `CSid` オブジェクトが有効でない場合、関数によってアサートが発生します。

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a> CSid:: GetSubAuthorityCount

Subauthority の数を返します。

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合、戻り値は subauthority count です。

メソッドが失敗した場合、戻り値は未定義になります。 オブジェクトが無効な場合、メソッドは失敗し `CSid` ます。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

> [!NOTE]
> デバッグビルドでは、 `CSid` オブジェクトが有効でない場合、関数によってアサートが発生します。

## <a name="csidisvalid"></a><a name="isvalid"></a> CSid:: IsValid

オブジェクトの `CSid` 有効性をテストします。

```
bool IsValid() const throw();
```

### <a name="return-value"></a>戻り値

`CSid`オブジェクトが有効な場合は TRUE、それ以外の場合は FALSE を返します。 このメソッドの拡張エラー情報はありません。を呼び出さないで `GetLastError` ください。

### <a name="remarks"></a>解説

メソッドは、 `IsValid` `CSid` リビジョン番号が既知の範囲内であり、サブ機関の数が最大値未満であることを確認することによって、オブジェクトを検証します。

## <a name="csidloadaccount"></a><a name="loadaccount"></a> CSid:: LoadAccount

指定されたアカウント名とドメイン、または既存の SID (セキュリティ識別子) 構造体で、`CSid` オブジェクトを更新します。

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>パラメーター

*pszAccountName*<br/>
アカウント名。

*pszSystem*<br/>
システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。

*pSid*<br/>
[SID](/windows/win32/api/winnt/ns-winnt-sid)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>解説

`LoadAccount` は、指定された名前でセキュリティ識別子の検索を試行します。 詳細については、「 [lookupaccountsid 関数](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) 」を参照してください。

## <a name="csidoperator-"></a><a name="operator_eq"></a> CSid:: operator =

代入演算子。

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`SID`オブジェクトに割り当てる (セキュリティ識別子) または `CSid` `CSid` 。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへの参照を返し `CSid` ます。

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a> CSid:: operator = =

2つのセキュリティ記述子オブジェクトが等しいかどうかをテストします。

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` = = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` = = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

セキュリティ記述子が等しい場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-"></a><a name="operator_neq"></a> CSid:: operator! =

2つのセキュリティ記述子オブジェクトが等しくないかどうかをテストします。

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` ! = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` ! = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

セキュリティ記述子が等しくない場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-lt"></a><a name="operator_lt"></a> CSid:: operator &lt;

2つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` ! = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` ! = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

*Lhs*が*rhs*未満の場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a> CSid:: operator &lt;=

2つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` ! = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` ! = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

*Lhs*が*rhs*以下の場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-gt"></a><a name="operator_gt"></a> CSid:: operator &gt;

2つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` ! = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` ! = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

*Lhs*が*rhs*より大きい場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a> CSid:: operator &gt;=

2つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` `CSid` ! = 演算子の左側に表示される (セキュリティ識別子) または。

*rhs*<br/>
`SID` `CSid` ! = 演算子の右側に表示される (セキュリティ識別子) または。

### <a name="return-value"></a>戻り値

*Lhs*が*rhs*以上の場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a> CSid:: operator const SID \*

オブジェクトを `CSid` `SID` (セキュリティ識別子) 構造体へのポインターにキャストします。

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>解説

構造体のアドレスを返し `SID` ます。

## <a name="csidsid"></a><a name="sid"></a> CSid:: Sid

`SID`(セキュリティ識別子) 構造体を文字列として返します。

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>戻り値

`SID`表示、保存、または転送に適した形式の文字列として構造体を返します。 [Convertsidtostringsid](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)に相当します。

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a> CSid:: SidNameUse

オブジェクトの状態の説明を返し `CSid` ます。

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの状態を示す値を格納するデータメンバーの値を返し `CSid` ます。

|値|説明|
|-----------|-----------------|
|SidTypeUser|ユーザー `SID` (セキュリティ識別子) を示します。|
|SidTypeGroup|グループを示し `SID` ます。|
|SidTypeDomain|ドメインを示し `SID` ます。|
|SidTypeAlias|エイリアスを示し `SID` ます。|
|SidTypeWellKnownGroup|`SID`よく知られているグループのを示します。|
|SidTypeDeletedAccount|`SID`削除されたアカウントのを示します。|
|SidTypeInvalid|が無効であることを示し `SID` ます。|
|SidTypeUnknown|不明な型を示し `SID` ます。|
|SidTypeComputer 場合|`SID`コンピューターのを示します。|

### <a name="remarks"></a>解説

を呼び出してから状態を返すには、 [CSid:: LoadAccount](#loadaccount) を呼び出してオブジェクトを更新し `CSid` `SidNameUse` ます。 `SidNameUse` は、またはを呼び出すことによってオブジェクトの状態を変更するのではなく `LookupAccountName` `LookupAccountSid` 、現在の状態のみを返します。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)<br/>
[演算子](../../atl/reference/atl-operators.md)
