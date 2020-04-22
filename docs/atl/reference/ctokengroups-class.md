---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: ccfa628f4a099f7e13eb09d272c72c2bdd846f37
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746381"
---
# <a name="ctokengroups-class"></a>クラス

このクラスは構造体のラッパー`TOKEN_GROUPS`です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CTokenGroups
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cトークングループ::Cトークングループ](#ctokengroups)|コンストラクターです。|
|[次のグループ:~Cトークングループ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cトークングループ::追加](#add)|オブジェクトに`CSid`既存`TOKEN_GROUPS`の構造体または`CTokenGroups`既存の構造体を追加します。|
|[Cトークングループ::Delete](#delete)|オブジェクトから`CSid`a およびその関連属性を`CTokenGroups`削除します。|
|[Cトークングループ::DeleteAll](#deleteall)|オブジェクトからすべての`CSid`オブジェクトと関連する属性を`CTokenGroups`削除します。|
|[次の値を取得します。](#getcount)|オブジェクトに含まれる`CSid`オブジェクトと関連する属性の数`CTokenGroups`を返します。|
|[次の値を取得します。](#getlength)|オブジェクトのサイズを`CTokenGroups`返します。|
|[Cトークングループ::GetPTOKEN_GROUPS](#getptoken_groups)|構造体へのポインターを`TOKEN_GROUPS`取得します。|
|[次の属性を取得します。](#getsidsandattributes)|オブジェクトに属`CSid`するオブジェクトと属性を`CTokenGroups`取得します。|
|[次の項目をグループ化します。](#lookupsid)|オブジェクトに関連付けられている属性を`CSid`取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[cトークングループ::演算子コンストTOKEN_GROUPS *](#operator_const_token_groups__star)|構造体への`CTokenGroups`ポインターにオブジェクトをキャストします`TOKEN_GROUPS`。|
|[Cトークングループ::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

[アクセス トークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティ コンテキストを記述するオブジェクトで、Windows システムにログオンしている各ユーザーに割り当てられます。

クラス`CTokenGroups`は、アクセス トークン内のグループ セキュリティ識別子 (SID) に関する情報を含む[、TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体のラッパーです。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="ctokengroupsadd"></a><a name="add"></a>Cトークングループ::追加

オブジェクトに`CSid`既存`TOKEN_GROUPS`の構造体または`CTokenGroups`既存の構造体を追加します。

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*dw属性*<br/>
`CSid`オブジェクトに関連付ける属性。

*グループ*<br/>
[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造。

### <a name="remarks"></a>解説

これらのメソッドは、1`CSid`つ以上のオブジェクトとそれに関連`CTokenGroups`付けられた属性をオブジェクトに追加します。

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a>Cトークングループ::Cトークングループ

コンストラクターです。

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
オブジェクトの構築[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)に使用する`CTokenGroups`オブジェクトまたはTOKEN_GROUPS構造体。 `CTokenGroups`

### <a name="remarks"></a>解説

オブジェクト`CTokenGroups`は、必要に応じて、構造体`TOKEN_GROUPS`または定義済みの`CTokenGroups`オブジェクトを使用して作成できます。

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a>次のグループ:~Cトークングループ

デストラクターです。

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>解説

デストラクタは、割り当てられたすべてのリソースを解放します。

## <a name="ctokengroupsdelete"></a><a name="delete"></a>Cトークングループ::Delete

オブジェクトから`CSid`a およびその関連属性を`CTokenGroups`削除します。

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
セキュリティ識別子 (SID) と属性を削除する必要がある[CSid](../../atl/reference/csid-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

が削除された`CSid`場合は true を返し、それ以外の場合は false を返します。

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a>Cトークングループ::DeleteAll

オブジェクトからすべての`CSid`オブジェクトと関連する属性を`CTokenGroups`削除します。

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a>次の値を取得します。

に含まれるオブジェクト`CSid`の数を`CTokenGroups`返します。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに含まれる[CSid](../../atl/reference/csid-class.md)オブジェクトと関連する属性の`CTokenGroups`数を返します。

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a>次の値を取得します。

オブジェクトのサイズを`CTokenGroup`返します。

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>解説

オブジェクトの合計サイズを`CTokenGroup`バイト単位で返します。

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a>Cトークングループ::GetPTOKEN_GROUPS

構造体へのポインターを`TOKEN_GROUPS`取得します。

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>戻り値

アクセス トークン オブジェクトに属する[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体への`CTokenGroups`ポインターを取得します。

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a>次の属性を取得します。

オブジェクトと、`CSid`オブジェクトに属する属性 (オプション) を`CTokenGroups`取得します。

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクトの配列へのポインター。

*属性*<br/>
DWORD の配列へのポインター。 このパラメーターを省略するか NULL にすると、属性は取得されません。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに含`CSid`まれるすべてのオブジェクトを`CTokenGroups`列挙し、それらを配置し、(オプションで) 属性フラグを配列オブジェクトに配置します。

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a>次の項目をグループ化します。

オブジェクトに関連付けられている属性を`CSid`取得します。

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*属性*<br/>
`CSid`オブジェクトの属性を受け入れる DWORD へのポインター。 省略または NULL の場合、属性は取得されません。

### <a name="return-value"></a>戻り値

が見つかった場合`CSid`は true を返し、そうでない場合は false を返します。

### <a name="remarks"></a>解説

*pdwAttributes*を NULL に設定すると、属性にアクセスせずに`CSid`、 の存在を確認できます。 このメソッドは、アクセス権のチェックには使用しないでください。 代わりに、アプリケーションは[C アクセス トークン::チェックトークン メンバーシップ](../../atl/reference/caccesstoken-class.md#checktokenmembership)メソッドを使用する必要があります。

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a>Cトークングループ::演算子 =

代入演算子。

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
オブジェクトに割[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)り当てる`CTokenGroups`オブジェクトまたはTOKEN_GROUPS構造。 `CTokenGroups`

### <a name="return-value"></a>戻り値

更新された`CTokenGroups`オブジェクトを返します。

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a>cトークングループ::演算子コンストTOKEN_GROUPS *

構造体へのポインターに値をキャストします`TOKEN_GROUPS`。

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>解説

[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体へのポインターに値をキャストします。

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[CSidクラス](../../atl/reference/csid-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
