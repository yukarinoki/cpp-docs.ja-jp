---
title: CMapPtrToPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::GetCount
- AFXCOLL/CMapPtrToPtr::GetHashTableSize
- AFXCOLL/CMapPtrToPtr::GetNextAssoc
- AFXCOLL/CMapPtrToPtr::GetSize
- AFXCOLL/CMapPtrToPtr::GetStartPosition
- AFXCOLL/CMapPtrToPtr::HashKey
- AFXCOLL/CMapPtrToPtr::InitHashTable
- AFXCOLL/CMapPtrToPtr::IsEmpty
- AFXCOLL/CMapPtrToPtr::Lookup
- AFXCOLL/CMapPtrToPtr::LookupKey
- AFXCOLL/CMapPtrToPtr::RemoveAll
- AFXCOLL/CMapPtrToPtr::RemoveKey
- AFXCOLL/CMapPtrToPtr::SetAt
helpviewer_keywords:
- CMapPtrToPtr [MFC], CMapPtrToPtr
- CMapPtrToPtr [MFC], GetCount
- CMapPtrToPtr [MFC], GetHashTableSize
- CMapPtrToPtr [MFC], GetNextAssoc
- CMapPtrToPtr [MFC], GetSize
- CMapPtrToPtr [MFC], GetStartPosition
- CMapPtrToPtr [MFC], HashKey
- CMapPtrToPtr [MFC], InitHashTable
- CMapPtrToPtr [MFC], IsEmpty
- CMapPtrToPtr [MFC], Lookup
- CMapPtrToPtr [MFC], LookupKey
- CMapPtrToPtr [MFC], RemoveAll
- CMapPtrToPtr [MFC], RemoveKey
- CMapPtrToPtr [MFC], SetAt
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
ms.openlocfilehash: b4ae511caab8278daf723bbcb8ffc5d57f5a1cd0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442668"
---
# <a name="cmapptrtoptr-class"></a>CMapPtrToPtr クラス

void ポインターをキーとした void ポインターのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapPtrToPtr : public CObject
```

## <a name="members"></a>メンバー

`CMapPtrToPtr` のメンバー関数は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 関数パラメーターまたは戻り値として `CObject` ポインターが表示されている場合は、ポインターを**void**に置き換えます。 関数パラメーターまたは戻り値として `CString` または**char**への**const**ポインターが表示されている場合は、ポインターを**void**に置き換えます。

`BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CMapPtrToPtr::CMapPtrToPtr](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CMapPtrToPtr:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapPtrToPtr::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapPtrToPtr::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapPtrToPtr:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapPtrToPtr::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapPtrToPtr:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapPtrToPtr::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapPtrToPtr:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapPtrToPtr:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapPtrToPtr:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapPtrToPtr:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapPtrToPtr:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapPtrToPtr:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CMapPtrToPtr:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。 `SetAt`の場合は演算子を代入します。|

## <a name="remarks"></a>コメント

`CMapPtrToPtr` には、実行時の型へのアクセスをサポートし、`CDumpContext` オブジェクトへのダンプを行うための IMPLEMENT_DYNAMIC マクロが組み込まれています。 個々のマップ要素 (ポインター値) のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

ポインターからポインターへのマップはシリアル化できません。

`CMapPtrToPtr` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。

`CMapPtrToPtr`の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToPtr`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>参照

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
