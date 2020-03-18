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
ms.openlocfilehash: a2ffcf7ce7ee6eccc56382501a5969ddec6c9e22
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442599"
---
# <a name="cmapstringtostring-class"></a>CMapStringToString クラス

`CString` オブジェクトをキーとした `CString` オブジェクトのマップをサポートします。

## <a name="syntax"></a>構文

```
class CMapStringToString : public CObject
```

## <a name="members"></a>メンバー

`CMapStringToString` のメンバー関数は、 [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)クラスのメンバー関数に似ています。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 戻り値または "出力" 関数のパラメーターとして `CObject` ポインターが表示されている場合は、ポインターを**char**に置き換えます。 `CObject` ポインターが "入力" 関数パラメーターとして表示されている場合は、ポインターを**char**に置き換えます。

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

たとえば、次のように変換します。

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>パブリック構造体

|Name|説明|
|----------|-----------------|
|[CMapStringToString::CPair](#cpair)|キー値と、関連付けられている文字列オブジェクトの値を格納している入れ子構造体。|

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CMapStringToString::CMapStringToString](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CMapStringToString:: GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|
|[CMapStringToString::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapStringToString::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapStringToString:: GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|
|[CMapStringToString::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|
|[CMapStringToString:: HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapStringToString::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapStringToString:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapStringToString:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapStringToString:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapStringToString::P GetFirstAssoc](#pgetfirstassoc)|Map 内の最初の `CString` へのポインターを取得します。|
|[CMapStringToString::P GetNextAssoc](#pgetnextassoc)|反復処理の対象となる次の `CString` へのポインターを取得します。|
|[CMapStringToString::P 参照](#plookup)|値が指定した値と一致する `CString` へのポインターを返します。|
|[CMapStringToString:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|
|[CMapStringToString:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定された要素を削除します。|
|[CMapStringToString:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CMapStringToString:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入します。 `SetAt`の場合は演算子を代入します。|

## <a name="remarks"></a>コメント

`CMapStringToString` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素は、マップがアーカイブに格納されている場合は、オーバーロードされた挿入 ( **<<** ) 演算子または `Serialize` メンバー関数と共にシリアル化されます。

個々の `CString`- `CString` 要素のダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

`CMapStringToString` オブジェクトが削除されるか、またはその要素が削除されると、`CString` オブジェクトが必要に応じて削除されます。

`CMapStringToString`の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

##  <a name="cpair"></a>CMapStringToString::CPair

キーの値と、関連付けられている文字列オブジェクトの値を格納します。

### <a name="remarks"></a>コメント

これは、クラス[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)内の入れ子構造です。

構造体は、次の2つのフィールドで構成されます。

- キーの種類の実際の値を `key` します。

- 関連付けられたオブジェクトの値を `value` します。

[CMapStringToString::P lookup](#plookup)、 [CMapStringToString::P getfirstassoc](#pgetfirstassoc)、および[CMapStringToString::P getnextassoc](#pgetnextassoc)からの戻り値を格納するために使用されます。

### <a name="example"></a>例

  使用例については、「 [CMapStringToString::P lookup](#plookup)」の例を参照してください。

##  <a name="pgetfirstassoc"></a>CMapStringToString::P GetFirstAssoc

Map オブジェクトの最初のエントリを返します。

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>戻り値

Map 内の最初のエントリへのポインター。「 [CMapStringToString:: CPair](#cpair)」を参照してください。 マップが空の場合、値は NULL になります。

### <a name="remarks"></a>コメント

この関数を呼び出して、map オブジェクト内の最初の要素を指すポインターを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

##  <a name="pgetnextassoc"></a>CMapStringToString::P GetNextAssoc

*によって*ポイントされるマップ要素を取得します。

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>パラメーター

*パスワード*<br/>
前の[PGetNextAssoc](#pgetnextassoc)呼び出しまたは[Pgetfirstassoc](#pgetfirstassoc)呼び出しによって返されたマップエントリを指します。

### <a name="return-value"></a>戻り値

Map 内の次のエントリへのポインター。「 [CMapStringToString:: CPair](#cpair)」を参照してください。 Map 内の最後の要素である場合、値は NULL になります。

### <a name="remarks"></a>コメント

Map 内のすべての要素を反復処理するには、このメソッドを呼び出します。 `PGetFirstAssoc` の呼び出しを使用して最初の要素を取得した後、`PGetNextAssoc`の連続した呼び出しでマップを反復処理します。

### <a name="example"></a>例

  [CMapStringToString::P GetFirstAssoc](#pgetfirstassoc)の例を参照してください。

##  <a name="plookup"></a>CMapStringToString::P 参照

指定されたキーにマップされている値を検索します。

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象の要素のキーへのポインター。

### <a name="return-value"></a>戻り値

指定されたキーへのポインター。

### <a name="remarks"></a>コメント

指定したキーと完全に一致するキーを持つマップ要素を検索するには、このメソッドを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>参照

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
