---
title: CMap クラス
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: 9a3c92a0a8c3d40e4cc3d289cc0221ff7cdb2e11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370095"
---
# <a name="cmap-class"></a>CMap クラス

一意なキーを値に割り当てる辞書コレクション クラスです。

## <a name="syntax"></a>構文

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>パラメーター

*キー*<br/>
マップのキーとして使用されるオブジェクトのクラス。

*ARG_KEY*<br/>
*KEY*引数に使用されるデータ型。通常は*KEY*への参照です。

*値*<br/>
マップに格納されているオブジェクトのクラス。

*ARG_VALUE*<br/>
*VALUE*引数に使用されるデータ型。通常は*VALUE*への参照です。

## <a name="members"></a>メンバー

### <a name="public-structures"></a>公共構造

|名前|説明|
|----------|-----------------|
|[CMap::ペア](#cpair)|キー値と関連オブジェクトの値を含むネストされた構造体。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMap::CMap](#cmap)|キーを値にマップするコレクションを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[::カウントを取得します。](#getcount)|このマップ内の要素の数を返します。|
|[次の表の値を指定します。](#gethashtablesize)|ハッシュ テーブル内の要素の数を返します。|
|[CMap::ゲットネクストアソック](#getnextassoc)|反復処理の次の要素を取得します。|
|[マップ::ゲットサイズ](#getsize)|このマップ内の要素の数を返します。|
|[::スタートポジション](#getstartposition)|最初の要素の位置を返します。|
|[次の表に従います。](#inithashtable)|ハッシュ テーブルを初期化し、そのサイズを指定します。|
|[CMap::IsEmpty](#isempty)|空のマップ条件 (要素なし) をテストします。|
|[CMap::ルックアップ](#lookup)|指定されたキーにマップされた値を調べています。|
|[CMap::Pファーストアソック](#pgetfirstassoc)|最初の要素へのポインターを返します。|
|[マップ::P次のアソック](#pgetnextassoc)|反復処理の次の要素へのポインターを取得します。|
|[検索:P](#plookup)|指定した値と一致する値を持つキーへのポインターを返します。|
|[CMap::すべて削除](#removeall)|このマップからすべての要素を削除します。|
|[キーの削除](#removekey)|キーで指定された要素を削除します。|
|[クマップ::セットアット](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CMap::演算子\[\]](#operator_at)|要素をマップに挿入します 。 `SetAt`|

## <a name="remarks"></a>解説

キーと値のペア (要素) をマップに挿入すると、キーを使用して効率的に取得または削除できます。 マップ内のすべての要素を反復処理することもできます。

POSITION タイプの変数は、項目への代替アクセスに使用されます。 POSITION を使用して、エントリを 「記憶」し、マップを反復処理できます。 この反復はキー値によって順次的に行われると思うかもしれません。そうじゃないです。 取得された要素のシーケンスは不確定です。

このクラスの特定のメンバー関数は、クラスのほとんどの使用に合わせてカスタマイズする必要があるグローバル`CMap`ヘルパ関数を呼び出します。 MFC リファレンスの「マクロとグローバル」の「[コレクション クラス ヘルパー](../../mfc/reference/collection-class-helpers.md) 」を**参照**してください。

`CMap`[CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドして、その要素のシリアル化とダンプをサポートします。 を使用して`Serialize`マップをアーカイブに格納する場合、各マップ要素は順番にシリアル化されます。 ヘルパー関数の既定の`SerializeElements`実装では、ビットごとの書き込みが行われます。 ポインター コレクション項目`CObject`のシリアル化の詳細については、「方法 : タイプ[セーフ コレクションを作成する](../../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。

マップ内の個々の要素 (キーと値) の診断ダンプが必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

オブジェクトが`CMap`削除されたとき、またはその要素が削除されると、キーと値の両方が削除されます。

マップ クラスの派生は、リストの派生に似ています。 特殊目的リスト クラスの派生の例については、記事[の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a>CMap::CMap

空のマップを作成します。

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
マップを拡張するためのメモリ割り当ての粒度を指定します。

### <a name="remarks"></a>解説

マップが大きくなると、メモリは*nBlockSize*エントリの単位で割り当てられます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a>CMap::ペア

キー値と関連オブジェクトの値を格納します。

### <a name="remarks"></a>解説

これはクラス[CMap](../../mfc/reference/cmap-class.md)内の入れ子構造です。

構造は、2 つのフィールドで構成されます。

- `key`キーの種類の実際の値。

- `value`関連付けられたオブジェクトの値。

これは[、CMap::P参照](#plookup)[、CMap::PGetFirstAssoc](#pgetfirstassoc)、および[CMap::PGetNextAssoc](#pgetnextassoc)からの戻り値を格納するために使用されます。

### <a name="example"></a>例

使用例については[、「CMap::PLookup](#plookup)の例」を参照してください。

## <a name="cmapgetcount"></a><a name="getcount"></a>::カウントを取得します。

マップ内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素の数。

### <a name="example"></a>例

[「CMap::Lookup」の例を参照](#lookup)してください。

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a>次の表の値を指定します。

マップのハッシュ テーブル内の要素の数を決定します。

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>戻り値

ハッシュ テーブル内の要素の数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::ゲットネクストアソック

で`rNextPosition`マップ要素を取得し、マップ内`rNextPosition`の次の要素を参照するように更新します。

```
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*次の位置*<br/>
前`GetNextAssoc`の呼び出しまたは`GetStartPosition`呼び出しによって返される POSITION 値への参照を指定します。

*キー*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*rキー*<br/>
取得した要素の返されたキーを指定します。

*値*<br/>
マップの値の型を指定するテンプレート パラメーター。

*Rvalue*<br/>
取得した要素の戻り値を指定します。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も便利です。 位置順序は、必ずしもキー値シーケンスと同じではありません。

取得した要素がマップ内の最後の要素である場合 *、rNextPosition*の新しい値は NULL に設定されます。

### <a name="example"></a>例

[CMap::SetAt](#setat)の例を参照してください。

## <a name="cmapgetsize"></a><a name="getsize"></a>マップ::ゲットサイズ

マップ要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

マップ内のアイテムの数。

### <a name="remarks"></a>解説

マップ内の要素の数を取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a>::スタートポジション

呼び出しに渡すことができる POSITION 値を返すことによって、`GetNextAssoc`マップの反復処理を開始します。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップを反復処理するための開始位置を示す POSITION 値。マップが空の場合は NULL。

### <a name="remarks"></a>解説

反復シーケンスは予測できません。したがって、「マップの最初の要素」には特別な意味はありません。

### <a name="example"></a>例

[CMap::SetAt](#setat)の例を参照してください。

## <a name="cmapinithashtable"></a><a name="inithashtable"></a>次の表に従います。

ハッシュ テーブルを初期化します。

```
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>パラメーター

*ハッシュサイズ*<br/>
ハッシュ テーブルのエントリ数。

*バロックナウ*<br/>
TRUE の場合は、初期化時にハッシュ テーブルを割り当てます。それ以外の場合は、必要に応じてテーブルが割り当てられます。

### <a name="remarks"></a>解説

最高のパフォーマンスを得る場合は、ハッシュ テーブルのサイズを素数にする必要があります。 衝突を最小限に抑えるには、サイズが予想される最大のデータセットよりも約 20% 大きい必要があります。

### <a name="example"></a>例

[「CMap::Lookup」の例を参照](#lookup)してください。

## <a name="cmapisempty"></a><a name="isempty"></a>CMap::IsEmpty

マップが空かどうかを判断します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このマップに要素が含まれなかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

[CMap::RemoveAll](#removeall)の例を参照してください。

## <a name="cmaplookup"></a><a name="lookup"></a>CMap::ルックアップ

指定されたキーにマップされた値を調べています。

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
*キー*値の型を指定するテンプレート パラメーター。

*key*<br/>
検索する要素を識別するキーを指定します。

*値*<br/>
検索する値の型を指定します。

*Rvalue*<br/>
検索された値を受け取ります。

### <a name="return-value"></a>戻り値

要素が見つかった場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

`Lookup`ハッシュ アルゴリズムを使用して、指定されたキーと正確に一致するキーを持つ map 要素をすばやく見つけることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a>CMap::演算子 [ ]

`SetAt`メンバー関数の代わりに便利です。

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>パラメーター

*値*<br/>
マップ値の型を指定するテンプレート パラメーター。

*ARG_KEY*<br/>
キー値の型を指定するテンプレート パラメーター。

*key*<br/>
マップから値を取得するために使用されるキー。

### <a name="remarks"></a>解説

したがって、代入ステートメントの左側 (左辺値) でのみ使用できます。 指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。

マップ内にキーが見つからない可能性があるため、この演算子と同等の"右辺"(r値)はありません。 要素を`Lookup`取得するには、メンバー関数を使用します。

### <a name="example"></a>例

[「CMap::Lookup」の例を参照](#lookup)してください。

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::Pファーストアソック

マップ オブジェクトの最初のエントリを返します。

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>戻り値

マップ内の最初のエントリへのポインター。[CMap::CPair を参照してください](#cpair)。 マップにエントリが含まれる場合、値は NULL になります。

### <a name="remarks"></a>解説

マップ オブジェクトの最初の要素をポインターを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a>マップ::P次のアソック

が指すマップ要素*を取得*します。

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>パラメーター

*パソクレ*<br/>
以前の[PGetNextAssoc](#pgetnextassoc)または[CMap::PGetFirstAssoc](#pgetfirstassoc)呼び出しによって返されたマップ エントリを指します。

### <a name="return-value"></a>戻り値

マップ内の次のエントリへのポインター。[CMap::CPair を参照してください](#cpair)。 要素がマップ内の最後の場合、値は NULL です。

### <a name="remarks"></a>解説

マップ内のすべての要素を反復処理します。 への呼び出しを使用して`PGetFirstAssoc`最初の要素を取得し、次にマップ`PGetNextAssoc`を反復処理して、連続してを呼び出します。

### <a name="example"></a>例

[「CMap::Pの例」](#pgetfirstassoc)を参照してください。

## <a name="cmapplookup"></a><a name="plookup"></a>検索:P

指定されたキーにマップされた値を検索します。

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象の要素のキー。

### <a name="return-value"></a>戻り値

キー構造体へのポインター。[CMap::CPair を参照してください](#cpair)。 一致するものが見つからない`CMap::PLookup`場合は、NULL を返します。

### <a name="remarks"></a>解説

指定したキーと完全に一致するキーを持つマップ要素を検索します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a>CMap::すべて削除

グローバル ヘルパー関数`DestructElements`を呼び出すことによって、このマップからすべての値を削除します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

マップが既に空の場合、関数は正しく動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a>キーの削除

指定されたキーに対応するマップ エントリを調えます。キーが見つかった場合は、エントリを削除します。

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
キーの種類を指定するテンプレート パラメーター。

*key*<br/>
削除する要素のキー。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

`DestructElements`ヘルパー関数は、エントリを削除するために使用されます。

### <a name="example"></a>例

[CMap::SetAt](#setat)の例を参照してください。

## <a name="cmapsetat"></a><a name="setat"></a>クマップ::セットアット

マップに要素を挿入する主な手段。

```
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
*キー*パラメータの型を指定するテンプレート パラメータ。

*key*<br/>
新しい要素のキーを指定します。

*ARG_VALUE*<br/>
*newValue*パラメーターの型を指定するテンプレート パラメーター。

*newValue*<br/>
新しい要素の値を指定します。

### <a name="remarks"></a>解説

まず、キーを検索します。 キーが見つかった場合は、対応する値が変更されます。それ以外の場合は、新しいキーと値のペアが作成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
