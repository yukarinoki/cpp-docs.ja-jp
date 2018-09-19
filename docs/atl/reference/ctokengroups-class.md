---
title: CTokenGroups クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d14a839cded7d22236912ba52a733a9ce15f7aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103244"
---
# <a name="ctokengroups-class"></a>CTokenGroups クラス

このクラスは、のラッパー、`TOKEN_GROUPS`構造体。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CTokenGroups
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|コンストラクターです。|
|[CTokenGroups:: ~ CTokenGroups](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTokenGroups::Add](#add)|追加、`CSid`または既存の`TOKEN_GROUPS`構造体を`CTokenGroups`オブジェクト。|
|[CTokenGroups::Delete](#delete)|削除、`CSid`とその関連付けられた属性から、`CTokenGroups`オブジェクト。|
|[CTokenGroups::DeleteAll](#deleteall)|すべてを削除します`CSid`オブジェクトと関連する属性から、`CTokenGroups`オブジェクト。|
|[CTokenGroups::GetCount](#getcount)|数を返します`CSid`オブジェクトと関連付けられている属性に含まれている、`CTokenGroups`オブジェクト。|
|[CTokenGroups::GetLength](#getlength)|サイズを返します、`CTokenGroups`オブジェクト。|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|ポインターを取得、`TOKEN_GROUPS`構造体。|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|取得、`CSid`オブジェクトと属性に属している、`CTokenGroups`オブジェクト。|
|[CTokenGroups::LookupSid](#lookupsid)|関連付けられている属性を取得、`CSid`オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|キャスト、`CTokenGroups`オブジェクトへのポインターを`TOKEN_GROUPS`構造体。|
|[CTokenGroups::operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

[アクセス トークン](/windows/desktop/SecAuthZ/access-tokens)プロセスまたはスレッドのセキュリティ コンテキストを示し、Windows システムにログオンしている各ユーザーに割り当てられているオブジェクトです。

`CTokenGroups`クラスは、のラッパー、 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)アクセス トークンのグループ セキュリティ識別子 (Sid) に関する情報を含む構造。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity.h

##  <a name="add"></a>  CTokenGroups::Add

追加、`CSid`または既存の`TOKEN_GROUPS`構造体を`CTokenGroups`オブジェクト。

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
A [CSid](../../atl/reference/csid-class.md)オブジェクト。

*dwAttributes*<br/>
関連付ける属性、`CSid`オブジェクト。

*rTokenGroups*<br/>
A [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)構造体。

### <a name="remarks"></a>Remarks

これらのメソッドが 1 つ以上追加`CSid`オブジェクトと関連する属性を`CTokenGroups`オブジェクト。

##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups

コンストラクターです。

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CTokenGroups`オブジェクトまたは[TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)構築に使用する構造体、`CTokenGroups`オブジェクト。

### <a name="remarks"></a>Remarks

`CTokenGroups`を使用してオブジェクトを作成することができます必要に応じて、`TOKEN_GROUPS`構造体または以前に定義された`CTokenGroups`オブジェクト。

##  <a name="dtor"></a>  CTokenGroups:: ~ CTokenGroups

デストラクターです。

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>Remarks

デストラクターは、割り当てられているすべてのリソースを解放します。

##  <a name="delete"></a>  CTokenGroups::Delete

削除、`CSid`とその関連付けられた属性から、`CTokenGroups`オブジェクト。

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)をセキュリティ識別子 (SID) と属性が削除されるオブジェクト。

### <a name="return-value"></a>戻り値

場合は true を返します、`CSid`が削除され、false それ以外の場合。

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

すべてを削除します`CSid`オブジェクトと関連する属性から、`CTokenGroups`オブジェクト。

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

数を返します`CSid`に含まれるオブジェクト`CTokenGroups`します。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

数を返します[CSid](../../atl/reference/csid-class.md)オブジェクトと関連する属性に含まれている、`CTokenGroups`オブジェクト。

##  <a name="getlength"></a>  CTokenGroups::GetLength

サイズを返します、`CTokenGroup`オブジェクト。

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>Remarks

合計サイズを返します、 `CTokenGroup` (バイト単位) のオブジェクト。

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

ポインターを取得、`TOKEN_GROUPS`構造体。

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>戻り値

ポインターを取得、 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)構造に属する、`CTokenGroups`アクセス トークンのオブジェクト。

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

取得、`CSid`オブジェクトと (必要に応じて) に属している属性、`CTokenGroups`オブジェクト。

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSids*<br/>
配列を指すポインター [CSid](../../atl/reference/csid-class.md)オブジェクト。

*pAttributes*<br/>
Dword の配列へのポインター。 このパラメーターが省略するか、NULL の場合は、属性は取得されません。

### <a name="remarks"></a>Remarks

このメソッドには、すべての列挙は、`CSid`オブジェクトに含まれている、`CTokenGroups`オブジェクト、配列オブジェクトと (必要に応じて) 属性フラグを配置します。

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

関連付けられている属性を取得、`CSid`オブジェクト。

```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*pdwAttributes*<br/>
そのまま使用する DWORD へのポインター、`CSid`オブジェクトの属性。 省略するか NULL の場合、属性は取得されません。

### <a name="return-value"></a>戻り値

場合は true を返します、`CSid`が見つかると、false それ以外の場合。

### <a name="remarks"></a>Remarks

設定*pdwAttributes*に NULL が存在することを確認する方法を提供する、`CSid`属性にアクセスしなくてもします。 アクセス権を確認するこのメソッドを使用しないことに注意してください。 代わりにアプリケーションを使用する必要があります、 [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership)メソッド。

##  <a name="operator_eq"></a>  CTokenGroups::operator =

代入演算子。

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CTokenGroups`オブジェクトまたは[TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)構造に割り当てる、`CTokenGroups`オブジェクト。

### <a name="return-value"></a>戻り値

更新された返します`CTokenGroups`オブジェクト。

##  <a name="operator_const_token_groups__star"></a>  CTokenGroups::operator const TOKEN_GROUPS *

値へのポインターにキャスト、`TOKEN_GROUPS`構造体。

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>Remarks

値へのポインターにキャスト、 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups)構造体。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../visual-cpp-samples.md)<br/>
[CSid クラス](../../atl/reference/csid-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
