---
title: CMapStringToString クラス
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToString::CMapStringToString
- AFXCOLL/CMapStringToString::GetCount
- AFXCOLL/CMapStringToString::GetHashTableSize
- AFXCOLL/CMapStringToString::GetNextAssoc
- AFXCOLL/CMapStringToString::GetSize
- AFXCOLL/CMapStringToString::GetStartPosition
- AFXCOLL/CMapStringToString::HashKey
- AFXCOLL/CMapStringToString::InitHashTable
- AFXCOLL/CMapStringToString::IsEmpty
- AFXCOLL/CMapStringToString::Lookup
- AFXCOLL/CMapStringToString::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToString::RemoveAll
- AFXCOLL/CMapStringToString::RemoveKey
- AFXCOLL/CMapStringToString::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToString [MFC], CMapStringToString
- CMapStringToString [MFC], GetCount
- CMapStringToString [MFC], GetHashTableSize
- CMapStringToString [MFC], GetNextAssoc
- CMapStringToString [MFC], GetSize
- CMapStringToString [MFC], GetStartPosition
- CMapStringToString [MFC], HashKey
- CMapStringToString [MFC], InitHashTable
- CMapStringToString [MFC], IsEmpty
- CMapStringToString [MFC], Lookup
- CMapStringToString [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToString [MFC], RemoveAll
- CMapStringToString [MFC], RemoveKey
- CMapStringToString [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 544154569c50369b805ba296aa975849f245d4ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370119"
---
# <a name="cmapstringtostring-class"></a>CMapStringToString クラス

`CString` オブジェクトをキーとした `CString` オブジェクトのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapStringToString : public CObject
```

## <a name="members"></a>メンバー

のメンバー関数`CMapStringToString`は、クラス[CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)のメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 ポインターが`CObject`戻り値または "output" 関数パラメーターとして見える場所では、 **char**へのポインターを置き換えます。 ポインターが`CObject`"input" 関数パラメーターとして見える場所では、 **char**へのポインターを置き換えます。

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>公共構造

|名前|説明|
|----------|-----------------|
|[文字列を次の文字列に移動します。](#cpair)|キー値と関連付けられた文字列オブジェクトの値を含む入れ子になった構造体。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[文字列を次に文字列を指定します。](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[文字列を取得します。](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[文字列を次に示します。](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュ テーブル内の現在の要素数を決定します。|
|[文字列を取得します。](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の次の要素を取得します。|
|[文字列を取得します。](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[文字列を取得します。](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[文字列を次に示します。](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[文字列を次に示します。](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュ テーブルを初期化します。|
|[文字列を次に文字列に移動します。](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) をテストします。|
|[文字列を検索します。](../../mfc/reference/cmapstringtoob-class.md#lookup)|void ポインター キーに基づいて void ポインターを参照します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[文字列を検索します。](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定したキー値に関連付けられたキーへの参照を返します。|
|[文字列を:P](#pgetfirstassoc)|マップ内の最初`CString`のポインターを取得します。|
|[文字列を:P](#pgetnextassoc)|反復処理の次`CString`のポインターを取得します。|
|[文字列を:P。](#plookup)|指定した値と一`CString`致する値を持つ、 へのポインターを返します。|
|[文字列を移動します。](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[文字列を削除します。](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーで指定された要素を削除します。|
|[文字列を文字列に変換します。](../../mfc/reference/cmapstringtoob-class.md#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[文字列を次の文字列に移動します\[。\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|要素をマップに挿入します 。 `SetAt`|

## <a name="remarks"></a>解説

`CMapStringToString` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 マップがアーカイブに格納されている場合、各**<<**`Serialize`要素は順番にシリアル化されます。

`CString`- 個々`CString`の要素のダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

オブジェクトが`CMapStringToString`削除されたとき、または要素が削除されると、`CString`オブジェクトは必要に応じて削除されます。

の詳細については、 の記事を参照してください。 [Collections](../../mfc/collections.md) `CMapStringToString`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="cmapstringtostringcpair"></a><a name="cpair"></a>文字列を次の文字列に移動します。

キー値と、関連付けられた文字列オブジェクトの値を格納します。

### <a name="remarks"></a>解説

これはクラス[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)内の入れ子構造です。

構造は、2 つのフィールドで構成されます。

- `key`キーの種類の実際の値。

- `value`関連付けられたオブジェクトの値。

これは、から戻り値を格納するために使用 :P :P [:Pされます](#plookup)。 [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc) [CMapStringToString::PGetNextAssoc](#pgetnextassoc)

### <a name="example"></a>例

  使用例については、「検索文字列を[文字列に追加::P」の例を参照してください](#plookup)。

## <a name="cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>文字列を:P

マップ オブジェクトの最初のエントリを返します。

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>戻り値

マップ内の最初のエントリへのポインター。を参照してください[。](#cpair) マップが空の場合、値は NULL です。

### <a name="remarks"></a>解説

マップ オブジェクトの最初の要素をポインターを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

## <a name="cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>文字列を:P

が指すマップ要素*を取得*します。

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>パラメーター

*パソック*<br/>
以前の[PGetNextAssoc または PGetFirstAssoc](#pgetnextassoc)呼び出しによって返されたマップ エントリ[へのポイント](#pgetfirstassoc)。

### <a name="return-value"></a>戻り値

マップ内の次のエントリへのポインター。を参照してください[。](#cpair) 要素がマップ内の最後の場合、値は NULL です。

### <a name="remarks"></a>解説

マップ内のすべての要素を反復処理します。 への呼び出しを使用して`PGetFirstAssoc`最初の要素を取得し、次にマップ`PGetNextAssoc`を反復処理して、連続してを呼び出します。

### <a name="example"></a>例

  の例[:P](#pgetfirstassoc)を参照してください。

## <a name="cmapstringtostringplookup"></a><a name="plookup"></a>文字列を:P。

指定されたキーにマップされた値を調べています。

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象の要素のキーへのポインター。

### <a name="return-value"></a>戻り値

指定したキーへのポインター。

### <a name="remarks"></a>解説

指定したキーと完全に一致するキーを持つマップ要素を検索します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
