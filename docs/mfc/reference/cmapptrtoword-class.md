---
title: CMapPtrToWord クラス
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToWord
- AFXCOLL/CMapPtrToWord
- AFXCOLL/CMapPtrToWord::CMapPtrToWord
- AFXCOLL/CMapPtrToWord::GetCount
- AFXCOLL/CMapPtrToWord::GetHashTableSize
- AFXCOLL/CMapPtrToWord::GetNextAssoc
- AFXCOLL/CMapPtrToWord::GetSize
- AFXCOLL/CMapPtrToWord::GetStartPosition
- AFXCOLL/CMapPtrToWord::HashKey
- AFXCOLL/CMapPtrToWord::InitHashTable
- AFXCOLL/CMapPtrToWord::IsEmpty
- AFXCOLL/CMapPtrToWord::Lookup
- AFXCOLL/CMapPtrToWord::LookupKey
- AFXCOLL/CMapPtrToWord::RemoveAll
- AFXCOLL/CMapPtrToWord::RemoveKey
- AFXCOLL/CMapPtrToWord::SetAt
helpviewer_keywords:
- CMapPtrToWord [MFC], CMapPtrToWord
- CMapPtrToWord [MFC], GetCount
- CMapPtrToWord [MFC], GetHashTableSize
- CMapPtrToWord [MFC], GetNextAssoc
- CMapPtrToWord [MFC], GetSize
- CMapPtrToWord [MFC], GetStartPosition
- CMapPtrToWord [MFC], HashKey
- CMapPtrToWord [MFC], InitHashTable
- CMapPtrToWord [MFC], IsEmpty
- CMapPtrToWord [MFC], Lookup
- CMapPtrToWord [MFC], LookupKey
- CMapPtrToWord [MFC], RemoveAll
- CMapPtrToWord [MFC], RemoveKey
- CMapPtrToWord [MFC], SetAt
ms.assetid: 4631c6b6-d49f-49d9-adc0-1e0491e32d7b
ms.openlocfilehash: 698e306896fd62888a84b6d6ce55fb4c9678187b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442650"
---
# <a name="cmapptrtoword-class"></a>CMapPtrToWord クラス

void ポインターをキーとした 16 ビット ワードのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapPtrToWord : public CObject
```

## <a name="members"></a>メンバー

`CMapPtrToWord` のメンバー関数は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 関数パラメーターまたは戻り値として `CObject` ポインターが表示されている場合は、WORD を代わりに使用します。 関数パラメーターまたは戻り値として `CString` または**char**への**const**ポインターが表示されている場合は、ポインターを**void**に置き換えます。

`BOOL CMapPtrToWord::Lookup( const void* <key>, WORD& <rValue> ) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CMapPtrToWord::CMapPtrToWord](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CMapPtrToWord:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapPtrToWord::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapPtrToWord::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapPtrToWord:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapPtrToWord::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapPtrToWord:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapPtrToWord::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapPtrToWord:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapPtrToWord:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapPtrToWord:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapPtrToWord:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapPtrToWord:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapPtrToWord:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CMapPtrToWord:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。 `SetAt`の場合は演算子を代入します。|

## <a name="remarks"></a>コメント

`CMapWordToPtr` には、実行時の型へのアクセスをサポートし、`CDumpContext` オブジェクトへのダンプを行うための IMPLEMENT_DYNAMIC マクロが組み込まれています。 個々のマップ要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

ポインターからワードへのマップはシリアル化できません。

`CMapPtrToWord` オブジェクトが削除されるか、その要素が削除されると、ポインターと単語が削除されます。 キーポインターによって参照されるエンティティは削除されません。

`CMapPtrToWord`の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToWord`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>参照

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
