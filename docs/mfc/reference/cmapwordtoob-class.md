---
title: CMapWordToOb クラス
ms.date: 11/04/2016
f1_keywords:
- CMapWordToOb
- AFXCOLL/CMapWordToOb
- AFXCOLL/CMapWordToOb::CMapWordToOb
- AFXCOLL/CMapWordToOb::GetCount
- AFXCOLL/CMapWordToOb::GetHashTableSize
- AFXCOLL/CMapWordToOb::GetNextAssoc
- AFXCOLL/CMapWordToOb::GetSize
- AFXCOLL/CMapWordToOb::GetStartPosition
- AFXCOLL/CMapWordToOb::HashKey
- AFXCOLL/CMapWordToOb::InitHashTable
- AFXCOLL/CMapWordToOb::IsEmpty
- AFXCOLL/CMapWordToOb::Lookup
- AFXCOLL/CMapWordToOb::LookupKey
- AFXCOLL/CMapWordToOb::RemoveAll
- AFXCOLL/CMapWordToOb::RemoveKey
- AFXCOLL/CMapWordToOb::SetAt
helpviewer_keywords:
- CMapWordToOb [MFC], CMapWordToOb
- CMapWordToOb [MFC], GetCount
- CMapWordToOb [MFC], GetHashTableSize
- CMapWordToOb [MFC], GetNextAssoc
- CMapWordToOb [MFC], GetSize
- CMapWordToOb [MFC], GetStartPosition
- CMapWordToOb [MFC], HashKey
- CMapWordToOb [MFC], InitHashTable
- CMapWordToOb [MFC], IsEmpty
- CMapWordToOb [MFC], Lookup
- CMapWordToOb [MFC], LookupKey
- CMapWordToOb [MFC], RemoveAll
- CMapWordToOb [MFC], RemoveKey
- CMapWordToOb [MFC], SetAt
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
ms.openlocfilehash: 80d53f195ba98f853c86a4d9c38fa9fcda52da3b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442583"
---
# <a name="cmapwordtoob-class"></a>CMapWordToOb クラス

16 ビット ワードをキーとした `CObject` ポインターのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapWordToOb : public CObject
```

## <a name="members"></a>メンバー

`CMapWordToOb` のメンバー関数は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 関数パラメーターまたは戻り値として `CString` または**char**への**const**ポインターが表示されている場合は、代わりに WORD を使用します。

`BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CMapWordToOb::CMapWordToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CMapWordToOb:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapWordToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapWordToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapWordToOb:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapWordToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapWordToOb:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapWordToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapWordToOb:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapWordToOb:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapWordToOb:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapWordToOb:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapWordToOb:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapWordToOb:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CMapWordToOb:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。 `SetAt`の場合は演算子を代入します。|

## <a name="remarks"></a>コメント

`CMapWordToOb` には、要素のシリアル化とダンプをサポートするための IMPLEMENT_SERIAL マクロが組み込まれています。 各要素は、マップがアーカイブに格納されている場合は、オーバーロードされた挿入 ( **<<** ) 演算子または `Serialize` メンバー関数と共にシリアル化されます。

個々のワード `CObject` 要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

`CMapWordToOb` オブジェクトが削除されるか、またはその要素が削除されると、`CObject` ポインターが削除されます。 `CObject` ポインターによって参照されているオブジェクトは破棄されません。

`CMapWordToOb`の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToOb`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="see-also"></a>参照

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
