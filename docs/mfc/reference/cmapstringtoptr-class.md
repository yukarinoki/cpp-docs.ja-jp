---
title: CMapStringToPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CMapStringToPtr
- AFXCOLL/CMapStringToPtr
- AFXCOLL/CMapStringToPtr::CMapStringToPtr
- AFXCOLL/CMapStringToPtr::GetCount
- AFXCOLL/CMapStringToPtr::GetHashTableSize
- AFXCOLL/CMapStringToPtr::GetNextAssoc
- AFXCOLL/CMapStringToPtr::GetSize
- AFXCOLL/CMapStringToPtr::GetStartPosition
- AFXCOLL/CMapStringToPtr::HashKey
- AFXCOLL/CMapStringToPtr::InitHashTable
- AFXCOLL/CMapStringToPtr::IsEmpty
- AFXCOLL/CMapStringToPtr::Lookup
- AFXCOLL/CMapStringToPtr::LookupKey
- AFXCOLL/CMapStringToPtr::RemoveAll
- AFXCOLL/CMapStringToPtr::RemoveKey
- AFXCOLL/CMapStringToPtr::SetAt
helpviewer_keywords:
- CMapStringToPtr [MFC], CMapStringToPtr
- CMapStringToPtr [MFC], GetCount
- CMapStringToPtr [MFC], GetHashTableSize
- CMapStringToPtr [MFC], GetNextAssoc
- CMapStringToPtr [MFC], GetSize
- CMapStringToPtr [MFC], GetStartPosition
- CMapStringToPtr [MFC], HashKey
- CMapStringToPtr [MFC], InitHashTable
- CMapStringToPtr [MFC], IsEmpty
- CMapStringToPtr [MFC], Lookup
- CMapStringToPtr [MFC], LookupKey
- CMapStringToPtr [MFC], RemoveAll
- CMapStringToPtr [MFC], RemoveKey
- CMapStringToPtr [MFC], SetAt
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
ms.openlocfilehash: 26a606d5813a68b55d8fc555025ccef270a25766
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223019"
---
# <a name="cmapstringtoptr-class"></a>CMapStringToPtr クラス

`CString` オブジェクトをキーとした void ポインターのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapStringToPtr : public CObject
```

## <a name="members"></a>メンバー

のメンバー関数 `CMapStringToPtr` は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 `CObject`関数パラメーターまたは戻り値としてポインターが表示されている場合は、へのポインターを置き換え **`void`** ます。

`BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> ) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CMapStringToPtr::CMapStringToPtr](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CMapStringToPtr:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapStringToPtr::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapStringToPtr::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapStringToPtr:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapStringToPtr::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapStringToPtr:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapStringToPtr::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapStringToPtr:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapStringToPtr:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapStringToPtr:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapStringToPtr:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapStringToPtr:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapStringToPtr:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|[説明]|
|----------|-----------------|
|[CMapStringToPtr:: operator \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。に対する演算子の代入 `SetAt` 。|

## <a name="remarks"></a>解説

`CMapStringToPtr`には、実行時の型へのアクセスとオブジェクトへのダンプをサポートする IMPLEMENT_DYNAMIC マクロが組み込まれて `CDumpContext` います。 個々のマップ要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

文字列からポインターへのマップはシリアル化できません。

`CMapStringToPtr`オブジェクトが削除されるか、その要素が削除されると、 `CString` キーオブジェクトと単語が削除されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
