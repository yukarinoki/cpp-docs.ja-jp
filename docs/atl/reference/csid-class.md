---
title: CSidクラス
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
ms.openlocfilehash: 414cf428cebe8105d90b3add93cc7f1e76927c2a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330919"
---
# <a name="csid-class"></a>CSidクラス

このクラスは、(セキュリティ識別子`SID`) 構造体のラッパーです。

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
|[CSid::CSidアレイ](#csidarray)|`CSid` オブジェクトの配列。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSid::CSid](#csid)|コンストラクターです。|
|[CSid::~CSid](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSid::アカウント名](#accountname)|オブジェクトに関連付けられたアカウントの名前を`CSid`返します。|
|[CSid::Dオオイン](#domain)|オブジェクトに関連付けられたドメインの名前を`CSid`返します。|
|[CSid::イコールプレフィックス](#equalprefix)|等`SID`しいかのプレフィックス (セキュリティ識別子) をテストします。|
|[CSid::ゲットレングス](#getlength)|`CSid`オブジェクトの長さを返します。|
|[CSID::ゲットプシド](#getpsid)|構造体へのポインターを`SID`返します。|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|構造体へのポインターを`SID_IDENTIFIER_AUTHORITY`返します。|
|[CSid::サブオーソリティを取得します。](#getsubauthority)|構造体内の指定されたサブオー`SID`ソリティを返します。|
|[CSid::サブオーソリティカウント](#getsubauthoritycount)|サブオーソリティ数を返します。|
|[CSid::イズバリ](#isvalid)|オブジェクトの`CSid`有効性をテストします。|
|[CSid::ロードアカウント](#loadaccount)|アカウント名`CSid`とドメイン、または既存`SID`の構造を指定してオブジェクトを更新します。|
|[CSid::シド](#sid)|ID 文字列を返します。|
|[CSid::シドネームユース](#sidnameuse)|オブジェクトの状態の説明を`CSid`返します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 =](#operator_eq)|代入演算子。|
|[演算子の定数 SID *](#operator_const_sid__star)|`CSid`構造体へのポインターにオブジェクトをキャストします`SID`。|

### <a name="global-operators"></a>グローバル演算子

|||
|-|-|
|[演算子 ==](#operator_eq_eq)|2 つのセキュリティ記述子オブジェクトが等しいかテストします|
|[演算子 !=](#operator_neq)|2 つのセキュリティ記述子オブジェクトの不等式をテストします。|
|[演算子\<](#operator_lt)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[演算子>](#operator_gt)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[演算子\<=](#operator_lt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|
|[演算子>=](#operator_gt__eq)|2 つのセキュリティ記述子オブジェクトの相対値を比較します。|

## <a name="remarks"></a>解説

構造体`SID`は、ユーザーまたはグループを一意に識別するために使用される可変長構造体です。

アプリケーションは、構造体を`SID`直接変更するのではなく、このラッパー クラスで提供されているメソッドを使用する必要があります。 また[、「」、](security-global-functions.md#atlgetownersid)ア[トリセットオーナーシド、アトリセットグループシド](security-global-functions.md#atlsetgroupsid)、[およびア](security-global-functions.md#atlgetgroupsid)[トリセットオーナーシド](security-global-functions.md#atlsetownersid)も参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="csidaccountname"></a><a name="accountname"></a>CSid::アカウント名

オブジェクトに関連付けられたアカウントの名前を`CSid`返します。

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>戻り値

アカウントの名前を指す LPCTSTR を返します。

### <a name="remarks"></a>解説

このメソッドは、指定された`SID`(セキュリティ識別子) の名前を検索しようとします。 詳細については、「アカウント[Sid の詳細](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)」を参照してください。

のアカウント名`SID`が見つからない場合は、`AccountName`空の文字列を返します。 これは、ネットワーク タイムアウトによってこのメソッドが名前を見つけることができない場合に発生する可能性があります。 また、サインイン セッションを識別する など`SID`、対応するアカウント名のないセキュリティ識別子にも発生します。

## <a name="csidcsid"></a><a name="csid"></a>CSid::CSid

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
既存`CSid`のオブジェクトまたは`SID`(セキュリティ識別子) 構造体。

*識別子の権限*<br/>
権限。

*数*<br/>
サブオーソリティカウント。

*アカウント名*<br/>
アカウント名。

*システム*<br/>
システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。

*pSid*<br/>
`SID`構造体へのポインター。

### <a name="remarks"></a>解説

コンストラクターは、オブジェクトを`CSid`初期化するか、内部データ メンバーを*SidTypeInvalid*に設定するか、または既存`CSid`の 、 `SID`、 または既存のアカウントから設定をコピーします。

初期化が失敗した場合、コンストラクタは[CAtlException クラス](../../atl/reference/catlexception-class.md)をスローします。

## <a name="csidcsid"></a><a name="dtor"></a>CSid::~CSid

デストラクターです。

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>解説

デストラクターは、オブジェクトによって取得されたリソースを解放します。

## <a name="csidcsidarray"></a><a name="csidarray"></a>CSid::CSidアレイ

[CSid](../../atl/reference/csid-class.md)オブジェクトの配列。

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>解説

この typedef は、ACL (アクセス制御リスト) からセキュリティ識別子を取得するために使用できる配列の型を指定します。 [「CAcl::ゲットAclエントリ」](../../atl/reference/cacl-class.md#getaclentries)を参照してください。

## <a name="csiddomain"></a><a name="domain"></a>CSid::Dオオイン

オブジェクトに関連付けられたドメインの名前を`CSid`返します。

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>戻り値

ドメインへの`LPCTSTR`ポイントを返します。

### <a name="remarks"></a>解説

このメソッドは、指定された`SID`(セキュリティ識別子) の名前を検索しようとします。 詳細については、「アカウント[Sid の詳細](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)」を参照してください。

のアカウント名`SID`が見つからない場合は、`Domain`空の文字列としてドメインを返します。 これは、ネットワーク タイムアウトによってこのメソッドが名前を見つけることができない場合に発生する可能性があります。 また、サインイン セッションを識別する など`SID`、対応するアカウント名のないセキュリティ識別子にも発生します。

## <a name="csidequalprefix"></a><a name="equalprefix"></a>CSid::イコールプレフィックス

等`SID`しいかのプレフィックス (セキュリティ識別子) をテストします。

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
比較`SID`する (セキュリティ識別子)`CSid`構造体またはオブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[イコール プレフィックス Sid](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid)を参照してください。

## <a name="csidgetlength"></a><a name="getlength"></a>CSid::ゲットレングス

`CSid`オブジェクトの長さを返します。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

`CSid`オブジェクトの長さをバイト単位で返します。

### <a name="remarks"></a>解説

構造体が`CSid`有効でない場合、戻り値は未定義です。 を呼`GetLength`び出す前に[、CSid::IsValid](#isvalid)メンバー`CSid`関数を使用して、有効であることを確認します。

> [!NOTE]
> デバッグ ビルドでは、オブジェクトが有効でない場合、ASSERT が`CSid`実行されます。

## <a name="csidgetpsid"></a><a name="getpsid"></a>CSID::ゲットプシド

(セキュリティ識別子)`SID`構造体へのポインターを返します。

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>戻り値

`CSid`オブジェクトの基になる`SID`構造体のアドレスを返します。

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY

構造体へのポインターを`SID_IDENTIFIER_AUTHORITY`返します。

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>戻り値

メソッドが成功すると、構造体のアドレスが`SID_IDENTIFIER_AUTHORITY`返されます。 失敗した場合、戻り値は未定義です。 オブジェクトが`CSid`有効でない場合に失敗が発生する可能性があり、その場合[、CSid::IsValid](#isvalid)メソッドは FALSE を返します。 拡張エラー`GetLastError`情報を得るための関数を呼び出すことができます。

> [!NOTE]
> デバッグ ビルドでは、オブジェクトが有効でない場合、ASSERT が`CSid`実行されます。

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::サブオーソリティを取得します。

(セキュリティ識別子) 構造体で`SID`指定されたサブ機関を返します。

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>パラメーター

*大局的な権限*<br/>
サブオーソリティ。

### <a name="return-value"></a>戻り値

*nSubAuthority*によって参照されるサブオーソリティを返します。 サブオーソリティ値は、相対 ID (RID) です。

### <a name="remarks"></a>解説

*nSubAuthority*パラメーターは、メソッドが返すサブオーソリティ配列要素を識別するインデックス値を指定します。 このメソッドは、この値に対して検証テストを実行しません。 アプリケーションは、許容値の範囲を検出するために[CSid::GetSubAuthorityCount](#getsubauthoritycount)を呼び出すことができます。

> [!NOTE]
> デバッグ ビルドでは、オブジェクトが有効でない場合、ASSERT が`CSid`実行されます。

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::サブオーソリティカウント

サブオーソリティ数を返します。

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合、戻り値はサブオーソリティカウントです。

メソッドが失敗した場合、戻り値は未定義です。 オブジェクトが無効な場合`CSid`、メソッドは失敗します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

> [!NOTE]
> デバッグ ビルドでは、オブジェクトが有効でない場合、ASSERT が`CSid`実行されます。

## <a name="csidisvalid"></a><a name="isvalid"></a>CSid::イズバリ

オブジェクトの`CSid`有効性をテストします。

```
bool IsValid() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが`CSid`有効な場合は TRUE を返し、有効でない場合は FALSE を返します。 このメソッドには拡張エラー情報はありません。を呼び`GetLastError`出さない

### <a name="remarks"></a>解説

この`IsValid`メソッドは、リビジョン`CSid`番号が既知の範囲内にあり、サブ権限の数が最大値未満であることを検証することによって、オブジェクトを検証します。

## <a name="csidloadaccount"></a><a name="loadaccount"></a>CSid::ロードアカウント

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

*アカウント名*<br/>
アカウント名。

*システム*<br/>
システム名。 この文字列には、リモート コンピューターの名前を使用できます。 この文字列が NULL の場合は、代わりにローカル システムが使用されます。

*pSid*<br/>
[SID](/windows/win32/api/winnt/ns-winnt-sid)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。

### <a name="remarks"></a>解説

`LoadAccount` は、指定された名前でセキュリティ識別子の検索を試行します。 詳細については[、LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)を参照してください。

## <a name="csidoperator-"></a><a name="operator_eq"></a>CSid::演算子 =

代入演算子。

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
(`SID`セキュリティ識別子) または`CSid`オブジェクトに割り`CSid`当てる。

### <a name="return-value"></a>戻り値

更新された`CSid`オブジェクトへの参照を返します。

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a>CSid::演算子 ==

2 つのセキュリティ記述子オブジェクトが等しいかテストします。

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
== 演算子の`SID`左側`CSid`に表示される (セキュリティ識別子) または

*rhs*<br/>
== 演算子の`SID`右側`CSid`に表示される (セキュリティ識別子) または

### <a name="return-value"></a>戻り値

セキュリティ記述子が等しい場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-"></a><a name="operator_neq"></a>CSid::演算子 !=

2 つのセキュリティ記述子オブジェクトが不等式かどうかをテストします。

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の左側に表示されます。

*rhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の右側に表示されます。

### <a name="return-value"></a>戻り値

セキュリティ記述子が等しくない場合は TRUE、それ以外の場合は FALSE。

## <a name="csidoperator-lt"></a><a name="operator_lt"></a>CSid::演算子&lt;

2 つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の左側に表示されます。

*rhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の右側に表示されます。

### <a name="return-value"></a>戻り値

*lhs*が*rhs*より小さい場合は TRUE を返します。

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::演算子&lt;=

2 つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の左側に表示されます。

*rhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の右側に表示されます。

### <a name="return-value"></a>戻り値

*lhs*が*rhs*以下の場合は TRUE を返します。

## <a name="csidoperator-gt"></a><a name="operator_gt"></a>CSid::演算子&gt;

2 つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の左側に表示されます。

*rhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の右側に表示されます。

### <a name="return-value"></a>戻り値

*lhs*が*rhs*より大きい場合は TRUE を返します。

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::演算子&gt;=

2 つのセキュリティ記述子オブジェクトの相対値を比較します。

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>パラメーター

*lhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の左側に表示されます。

*rhs*<br/>
`SID` (セキュリティ識別子) または`CSid`!= 演算子の右側に表示されます。

### <a name="return-value"></a>戻り値

*lhs*が*rhs*以上の場合は TRUE を返します。

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::演算子の定数 SID\*

オブジェクトを`CSid`(セキュリティ識別子) 構造体`SID`へのポインターにキャストします。

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>解説

構造体のアドレスを`SID`返します。

## <a name="csidsid"></a><a name="sid"></a>CSid::シド

`SID` (セキュリティ識別子) 構造体を文字列として返します。

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>戻り値

表示、`SID`保存、または伝送に適した形式で構造体を文字列として返します。 変換と同等[の文字列を設定します](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)。

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a>CSid::シドネームユース

オブジェクトの状態の説明を`CSid`返します。

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの状態を説明する値を格納するデータ メンバーの値を`CSid`返します。

|[値]|説明|
|-----------|-----------------|
|シドタイプユーザー|ユーザー `SID` (セキュリティ識別子) を示します。|
|シドタイプグループ|グループ`SID`を示します。|
|シドタイプドメイン|ドメイン`SID`を示します。|
|シドタイプエイリアス|エイリアス`SID`を示します。|
|シドタイプウェルウェルウェルグループ|既知`SID`のグループの を示します。|
|アカウントの種類を削除しました|削除された`SID`アカウントの を示します。|
|Sid 型が無効です|無効`SID`な .|
|シドタイプ不明|不明`SID`な型を示します。|
|シドタイプコンピュータ|コンピュータの`SID`を示します。|

### <a name="remarks"></a>解説

[CSid::LoadAccount](#loadaccount)を呼び`CSid`出して、`SidNameUse`オブジェクトの状態を返すために呼び出す前にオブジェクトを更新します。 `SidNameUse`は、 or`LookupAccountName``LookupAccountSid`を呼び出すことによってオブジェクトの状態を変更するのではなく、現在の状態だけを返します。

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)<br/>
[オペレーター](../../atl/reference/atl-operators.md)
