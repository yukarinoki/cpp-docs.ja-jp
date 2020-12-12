---
description: '詳細情報: CTokenGroups クラス'
title: CTokenGroups クラス
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
ms.openlocfilehash: 3d6633afbd649aa175196f1fae8e62afdf784f99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140349"
---
# <a name="ctokengroups-class"></a>CTokenGroups クラス

このクラスは、構造体のラッパーです `TOKEN_GROUPS` 。

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
|[CTokenGroups:: CTokenGroups](#ctokengroups)|コンストラクターです。|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTokenGroups:: Add](#add)|`CSid`または既存 `TOKEN_GROUPS` の構造体をオブジェクトに追加し `CTokenGroups` ます。|
|[CTokenGroups::D e)](#delete)|`CSid`とそれに関連付けられている属性をオブジェクトから削除し `CTokenGroups` ます。|
|[CTokenGroups::D eleteAll](#deleteall)|オブジェクトからすべての `CSid` オブジェクトとそれに関連付けられている属性を削除 `CTokenGroups` します。|
|[CTokenGroups:: GetCount](#getcount)|`CSid`オブジェクトに格納されているオブジェクトと関連する属性の数を返し `CTokenGroups` ます。|
|[CTokenGroups:: GetLength](#getlength)|オブジェクトのサイズを返し `CTokenGroups` ます。|
|[CTokenGroups:: GetPTOKEN_GROUPS](#getptoken_groups)|構造体へのポインターを取得 `TOKEN_GROUPS` します。|
|[CTokenGroups:: GetSidsAndAttributes](#getsidsandattributes)|`CSid`オブジェクトに属するオブジェクトと属性を取得し `CTokenGroups` ます。|
|[CTokenGroups:: LookupSid](#lookupsid)|オブジェクトに関連付けられている属性を取得し `CSid` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTokenGroups:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|オブジェクトを `CTokenGroups` 構造体へのポインターにキャストし `TOKEN_GROUPS` ます。|
|[CTokenGroups:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

[アクセストークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティコンテキストを記述するオブジェクトで、Windows システムにログオンした各ユーザーに割り当てられます。

クラスは、 `CTokenGroups` アクセストークンのグループセキュリティ識別子 (sid) に関する情報を含む [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 構造体のラッパーです。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="ctokengroupsadd"></a><a name="add"></a> CTokenGroups:: Add

`CSid`または既存 `TOKEN_GROUPS` の構造体をオブジェクトに追加し `CTokenGroups` ます。

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*dwAttributes*<br/>
オブジェクトに関連付ける属性 `CSid` 。

*rTokenGroups*<br/>
[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体。

### <a name="remarks"></a>解説

これらのメソッドは、オブジェクトに1つ以上の `CSid` オブジェクトとそれに関連付けられている属性を追加し `CTokenGroups` ます。

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a> CTokenGroups:: CTokenGroups

コンストラクターです。

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CTokenGroups`オブジェクトの構築に使用するオブジェクトまたは[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体 `CTokenGroups` 。

### <a name="remarks"></a>解説

オブジェクトは、 `CTokenGroups` 必要に応じて、構造体または以前に定義したオブジェクトを使用して作成でき `TOKEN_GROUPS` `CTokenGroups` ます。

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a> CTokenGroups:: ~ CTokenGroups

デストラクターです。

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>解説

デストラクターは、割り当てられたすべてのリソースを解放します。

## <a name="ctokengroupsdelete"></a><a name="delete"></a> CTokenGroups::D e)

`CSid`とそれに関連付けられている属性をオブジェクトから削除し `CTokenGroups` ます。

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
セキュリティ識別子 (SID) と属性を削除する必要がある [CSid](../../atl/reference/csid-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

が削除された場合は true、それ以外の場合は false を返し `CSid` ます。

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a> CTokenGroups::D eleteAll

オブジェクトからすべての `CSid` オブジェクトとそれに関連付けられている属性を削除 `CTokenGroups` します。

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a> CTokenGroups:: GetCount

に格納されているオブジェクトの数を返し `CSid` `CTokenGroups` ます。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに格納されている [CSid](../../atl/reference/csid-class.md) オブジェクトとそれに関連付けられている属性の数を返し `CTokenGroups` ます。

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a> CTokenGroups:: GetLength

オブジェクトのサイズを返し `CTokenGroup` ます。

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>解説

オブジェクトの合計サイズ `CTokenGroup` をバイト単位で返します。

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a> CTokenGroups:: GetPTOKEN_GROUPS

構造体へのポインターを取得 `TOKEN_GROUPS` します。

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>戻り値

アクセストークンオブジェクトに属する [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 構造体へのポインターを取得 `CTokenGroups` します。

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a> CTokenGroups:: GetSidsAndAttributes

オブジェクト、 `CSid` および (オプションで) オブジェクトに属する属性を取得し `CTokenGroups` ます。

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクトの配列へのポインター。

*pAttributes*<br/>
Dword の配列へのポインター。 このパラメーターを省略した場合、または NULL の場合、属性は取得されません。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに格納されているすべてのオブジェクトを列挙し、それらのオブジェクト `CSid` `CTokenGroups` と (必要に応じて) 属性フラグを配列オブジェクトに格納します。

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a> CTokenGroups:: LookupSid

オブジェクトに関連付けられている属性を取得し `CSid` ます。

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*pdwAttributes*<br/>
オブジェクトの属性を受け取る DWORD へのポインター `CSid` 。 省略した場合、または NULL の場合、属性は取得されません。

### <a name="return-value"></a>戻り値

が見つかった場合は true、それ以外の場合は false を返し `CSid` ます。

### <a name="remarks"></a>解説

*PdwAttributes* を NULL に設定すると、属性にアクセスせずにの存在を確認することが `CSid` できます。 アクセス権を確認するためにこの方法を使用することはできないことに注意してください。 アプリケーションでは、代わりに [CAccessToken:: CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) メソッドを使用する必要があります。

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a> CTokenGroups:: operator =

代入演算子。

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CTokenGroups`オブジェクトに割り当てるオブジェクトまたは[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)構造体 `CTokenGroups` 。

### <a name="return-value"></a>戻り値

更新されたオブジェクトを返し `CTokenGroups` ます。

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a> CTokenGroups:: operator const TOKEN_GROUPS *

構造体へのポインターに値をキャスト `TOKEN_GROUPS` します。

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>解説

値を [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 構造体へのポインターにキャストします。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[CSid クラス](../../atl/reference/csid-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
