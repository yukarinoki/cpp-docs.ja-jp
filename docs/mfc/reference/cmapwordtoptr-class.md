---
description: '詳細情報: CMapWordToPtr クラス'
title: CMapWordToPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CMapWordToPtr
- AFXCOLL/CMapWordToPtr
- AFXCOLL/CMapWordToPtr::CMapWordToPtr
- AFXCOLL/CMapWordToPtr::GetCount
- AFXCOLL/CMapWordToPtr::GetHashTableSize
- AFXCOLL/CMapWordToPtr::GetNextAssoc
- AFXCOLL/CMapWordToPtr::GetSize
- AFXCOLL/CMapWordToPtr::GetStartPosition
- AFXCOLL/CMapWordToPtr::HashKey
- AFXCOLL/CMapWordToPtr::InitHashTable
- AFXCOLL/CMapWordToPtr::IsEmpty
- AFXCOLL/CMapWordToPtr::Lookup
- AFXCOLL/CMapWordToPtr::LookupKey
- AFXCOLL/CMapWordToPtr::RemoveAll
- AFXCOLL/CMapWordToPtr::RemoveKey
- AFXCOLL/CMapWordToPtr::SetAt
helpviewer_keywords:
- CMapWordToPtr [MFC], CMapWordToPtr
- CMapWordToPtr [MFC], GetCount
- CMapWordToPtr [MFC], GetHashTableSize
- CMapWordToPtr [MFC], GetNextAssoc
- CMapWordToPtr [MFC], GetSize
- CMapWordToPtr [MFC], GetStartPosition
- CMapWordToPtr [MFC], HashKey
- CMapWordToPtr [MFC], InitHashTable
- CMapWordToPtr [MFC], IsEmpty
- CMapWordToPtr [MFC], Lookup
- CMapWordToPtr [MFC], LookupKey
- CMapWordToPtr [MFC], RemoveAll
- CMapWordToPtr [MFC], RemoveKey
- CMapWordToPtr [MFC], SetAt
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
ms.openlocfilehash: ea260d785b2edf056cdf3b5bc1ef1c79564f5dc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207801"
---
# <a name="cmapwordtoptr-class"></a>CMapWordToPtr クラス

16 ビット ワードをキーとした void ポインターのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapWordToPtr : public CObject
```

## <a name="members"></a>メンバー

のメンバー関数 `CMapWordToPtr` は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 `CObject`関数パラメーターまたは戻り値としてポインターが表示されている場合は、へのポインターを置き換え **`void`** ます。 `CString` **`const`** 関数パラメーターまたは戻り値として、またはへのポインターが表示されている場合は **`char`** 、WORD を置き換えます。

`BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMapWordToPtr::CMapWordToPtr](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMapWordToPtr:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapWordToPtr::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapWordToPtr::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapWordToPtr:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapWordToPtr::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapWordToPtr:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapWordToPtr::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapWordToPtr:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapWordToPtr:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapWordToPtr:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapWordToPtr:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapWordToPtr:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapWordToPtr:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CMapWordToPtr:: operator \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。に対する演算子の代入 `SetAt` 。|

## <a name="remarks"></a>解説

`CMapWordToPtr` には、実行時の型へのアクセスとオブジェクトへのダンプをサポートする IMPLEMENT_DYNAMIC マクロが組み込まれて `CDumpContext` います。 個々のマップ要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

ワードツーポインターマップはシリアル化できません。

`CMapWordToPtr`オブジェクトが削除されるか、その要素が削除されると、単語とポインターが削除されます。 ポインターによって参照されるエンティティは削除されません。

の詳細については `CMapWordToPtr` 、「 [コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToPtr`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
