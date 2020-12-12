---
description: '詳細情報: CMap クラス'
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
ms.openlocfilehash: ff88d205608cc87f06d28e6d2d4b647c35909efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207905"
---
# <a name="cmap-class"></a>CMap クラス

一意なキーを値に割り当てる辞書コレクション クラスです。

## <a name="syntax"></a>構文

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>パラメーター

*KEY*<br/>
マップのキーとして使用されるオブジェクトのクラス。

*ARG_KEY*<br/>
*キー* 引数に使用されるデータ型です。通常は、*キー* への参照です。

*VALUE*<br/>
Map に格納されているオブジェクトのクラス。

*ARG_VALUE*<br/>
*値* の引数に使用されるデータ型です。通常、*値* への参照です。

## <a name="members"></a>メンバー

### <a name="public-structures"></a>パブリック構造体

|名前|説明|
|----------|-----------------|
|[CMap:: CPair](#cpair)|キー値と、関連付けられたオブジェクトの値を格納している入れ子構造体。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMap:: CMap](#cmap)|キーを値に割り当てるコレクションを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMap:: GetCount](#getcount)|このマップ内の要素の数を返します。|
|[CMap:: GetHashTableSize](#gethashtablesize)|ハッシュテーブル内の要素の数を返します。|
|[CMap:: GetNextAssoc](#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMap:: GetSize](#getsize)|このマップ内の要素の数を返します。|
|[CMap:: GetStartPosition](#getstartposition)|最初の要素の位置を返します。|
|[CMap:: InitHashTable](#inithashtable)|ハッシュテーブルを初期化し、そのサイズを指定します。|
|[CMap:: IsEmpty](#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMap:: Lookup](#lookup)|指定されたキーにマップされている値を検索します。|
|[CMap: GetFirstAssoc を:P](#pgetfirstassoc)|最初の要素へのポインターを返します。|
|[CMap::P GetNextAssoc](#pgetnextassoc)|反復処理の対象となる次の要素へのポインターを取得します。|
|[CMap::P 参照](#plookup)|値が指定した値と一致するキーへのポインターを返します。|
|[CMap:: RemoveAll](#removeall)|このマップからすべての要素を削除します。|
|[CMap:: RemoveKey](#removekey)|キーによって指定された要素を削除します。|
|[CMap:: SetAt](#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CMap:: 演算子 \[\]](#operator_at)|Map に要素を挿入します。に対する演算子の代入 `SetAt` 。|

## <a name="remarks"></a>解説

キーと値のペア (要素) をマップに挿入すると、キーを使用してペアを効率的に取得または削除できます。 また、マップ内のすべての要素を反復処理することもできます。

POSITION 型の変数は、エントリへの代替アクセスに使用されます。 位置を使用して、エントリを "記憶" し、マップを反復処理することができます。 このイテレーションはキー値によって連続していると思われるかもしれません。そうじゃないです。 取得された要素のシーケンスは不確定です。

このクラスの特定のメンバー関数は、クラスのほとんどの用途に合わせてカスタマイズする必要があるグローバルヘルパー関数を呼び出し `CMap` ます。 **MFC リファレンス** の「マクロとグローバル」の「[コレクションクラスヘルパー](../../mfc/reference/collection-class-helpers.md) 」を参照してください。

`CMap`[CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドして、その要素のシリアル化とダンプをサポートします。 を使用してマップがアーカイブに格納されている場合 `Serialize` 、各マップ要素は順番にシリアル化されます。 ヘルパー関数の既定の実装で `SerializeElements` は、ビットごとの書き込みが行われます。 またはその他のユーザー定義型から派生したポインターコレクション項目のシリアル化の詳細につい `CObject` ては、「 [方法: Type-Safe コレクションを作成](../../mfc/how-to-make-a-type-safe-collection.md)する」を参照してください。

マップ内の個々の要素 (キーと値) の診断ダンプが必要な場合は、ダンプコンテキストの深さを1以上に設定する必要があります。

`CMap`オブジェクトが削除されるか、その要素が削除されると、キーと値の両方が削除されます。

マップクラスの派生は、リストの派生に似ています。 特別な目的のリストクラスの派生の図解については、「 [コレクション](../../mfc/collections.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>要件

**ヘッダー:** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a> CMap:: CMap

空のマップを構築します。

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
マップを拡張するためのメモリ割り当ての粒度を指定します。

### <a name="remarks"></a>解説

マップが大きくなるにつれて、メモリは *Nblocksize* エントリの単位で割り当てられます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a> CMap:: CPair

キー値と、関連付けられたオブジェクトの値を格納します。

### <a name="remarks"></a>解説

これは、クラス [CMap](../../mfc/reference/cmap-class.md)内の入れ子構造です。

構造体は、次の2つのフィールドで構成されます。

- `key` キーの型の実際の値。

- `value` 関連付けられたオブジェクトの値。

これは、 [cmap::P lookup](#plookup)、 [Cmap::P getfirstassoc](#pgetfirstassoc)、および [cmap::P getnextassoc](#pgetnextassoc)からの戻り値を格納するために使用されます。

### <a name="example"></a>例

使用例については、「 [CMap::P lookup](#plookup)」の例を参照してください。

## <a name="cmapgetcount"></a><a name="getcount"></a> CMap:: GetCount

Map 内の要素の数を取得します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

要素の数。

### <a name="example"></a>例

「 [CMap:: Lookup](#lookup)」の例を参照してください。

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a> CMap:: GetHashTableSize

マップのハッシュテーブル内の要素の数を決定します。

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>戻り値

ハッシュテーブル内の要素の数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a> CMap:: GetNextAssoc

で map 要素を取得 `rNextPosition` し、を更新し `rNextPosition` て、マップ内の次の要素を参照します。

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*rNextPosition*<br/>
前のまたは呼び出しによって返される位置値への参照を指定し `GetNextAssoc` `GetStartPosition` ます。

*KEY*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*rKey*<br/>
取得した要素の返されたキーを指定します。

*VALUE*<br/>
マップの値の型を指定するテンプレートパラメーター。

*右辺値*<br/>
取得した要素の戻り値を指定します。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も役立ちます。 位置シーケンスは必ずしもキー値のシーケンスと同じではないことに注意してください。

取得した要素が map 内の最後の要素である場合、 *Rnextposition* の新しい値は NULL に設定されます。

### <a name="example"></a>例

[CMap:: SetAt](#setat)の例を参照してください。

## <a name="cmapgetsize"></a><a name="getsize"></a> CMap:: GetSize

マップ要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

マップ内のアイテムの数。

### <a name="remarks"></a>解説

Map 内の要素の数を取得するには、このメソッドを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a> CMap:: GetStartPosition

呼び出しに渡すことができる位置の値を返すことによって、マップの反復処理を開始し `GetNextAssoc` ます。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップの反復処理の開始位置を示す位置の値です。または、マップが空の場合は NULL になります。

### <a name="remarks"></a>解説

イテレーションシーケンスは予測できません。したがって、"map 内の最初の要素" には特別な意味はありません。

### <a name="example"></a>例

[CMap:: SetAt](#setat)の例を参照してください。

## <a name="cmapinithashtable"></a><a name="inithashtable"></a> CMap:: InitHashTable

ハッシュテーブルを初期化します。

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>パラメーター

*hashSize*<br/>
ハッシュテーブル内のエントリの数。

*今すぐ*<br/>
TRUE の場合、初期化時にハッシュテーブルを割り当てます。それ以外の場合は、必要に応じてテーブルが割り当てられます。

### <a name="remarks"></a>解説

最適なパフォーマンスを得るには、ハッシュテーブルのサイズを素数にする必要があります。 競合を最小限に抑えるには、予想される最大のデータセットよりもサイズを約20% 大きくする必要があります。

### <a name="example"></a>例

「 [CMap:: Lookup](#lookup)」の例を参照してください。

## <a name="cmapisempty"></a><a name="isempty"></a> CMap:: IsEmpty

マップが空かどうかを判断します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このマップに要素が含まれていない場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[CMap:: RemoveAll](#removeall)の例を参照してください。

## <a name="cmaplookup"></a><a name="lookup"></a> CMap:: Lookup

指定されたキーにマップされている値を検索します。

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
*キー* 値の型を指定するテンプレートパラメーター。

*key*<br/>
検索する要素を識別するキーを指定します。

*VALUE*<br/>
検索する値の型を指定します。

*右辺値*<br/>
検索された値を受け取ります。

### <a name="return-value"></a>戻り値

要素が見つかった場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

`Lookup` ハッシュアルゴリズムを使用して、指定されたキーと完全に一致するキーを持つ map 要素をすばやく検索します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a> CMap:: operator []

メンバー関数の便利な代替手段 `SetAt` 。

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>パラメーター

*VALUE*<br/>
マップ値の型を指定するテンプレートパラメーター。

*ARG_KEY*<br/>
キー値の型を指定するテンプレートパラメーター。

*key*<br/>
マップから値を取得するために使用するキー。

### <a name="remarks"></a>解説

したがって、代入ステートメント (左辺値) の左側でのみ使用できます。 指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。

マップ内にキーが見つからない可能性があるため、この演算子に相当する "右辺" (r 値) はありません。 `Lookup`要素の取得には、メンバー関数を使用します。

### <a name="example"></a>例

「 [CMap:: Lookup](#lookup)」の例を参照してください。

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a> CMap: GetFirstAssoc を:P

Map オブジェクトの最初のエントリを返します。

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>戻り値

Map 内の最初のエントリへのポインター。「 [CMap:: CPair](#cpair)」を参照してください。 マップにエントリが含まれていない場合、値は NULL になります。

### <a name="remarks"></a>解説

この関数を呼び出して、map オブジェクト内の最初の要素を指すポインターを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a> CMap::P GetNextAssoc

*によって* ポイントされるマップ要素を取得します。

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>パラメーター

*パスワード (& t)*<br/>
前の [PGetNextAssoc](#pgetnextassoc) または [CMap::P getfirstassoc](#pgetfirstassoc) 呼び出しによって返されたマップエントリを指します。

### <a name="return-value"></a>戻り値

Map 内の次のエントリへのポインター。「 [CMap:: CPair](#cpair)」を参照してください。 Map 内の最後の要素である場合、値は NULL になります。

### <a name="remarks"></a>解説

Map 内のすべての要素を反復処理するには、このメソッドを呼び出します。 の呼び出しを使用して最初の要素を取得し、 `PGetFirstAssoc` を連続して呼び出すことで map を反復処理し `PGetNextAssoc` ます。

### <a name="example"></a>例

「 [CMap::P GetFirstAssoc](#pgetfirstassoc)」の例を参照してください。

## <a name="cmapplookup"></a><a name="plookup"></a> CMap::P 参照

指定されたキーにマップされている値を検索します。

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象の要素のキー。

### <a name="return-value"></a>戻り値

キー構造体へのポインター。「 [CMap:: CPair](#cpair)」を参照してください。 一致するものが見つからない場合は、 `CMap::PLookup` NULL を返します。

### <a name="remarks"></a>解説

指定したキーと完全に一致するキーを持つマップ要素を検索するには、このメソッドを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a> CMap:: RemoveAll

グローバルヘルパー関数を呼び出すことによって、このマップからすべての値を削除し `DestructElements` ます。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

マップが既に空の場合、関数は正しく動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a> CMap:: RemoveKey

指定されたキーに対応するマップエントリを検索します。次に、キーが見つかった場合は、エントリを削除します。

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
キーの型を指定するテンプレートパラメーター。

*key*<br/>
削除する要素のキー。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

`DestructElements`ヘルパー関数は、エントリを削除するために使用されます。

### <a name="example"></a>例

[CMap:: SetAt](#setat)の例を参照してください。

## <a name="cmapsetat"></a><a name="setat"></a> CMap:: SetAt

主な手段は、map に要素を挿入することです。

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
*キー* パラメーターの型を指定するテンプレートパラメーター。

*key*<br/>
新しい要素のキーを指定します。

*ARG_VALUE*<br/>
*NewValue* パラメーターの型を指定するテンプレートパラメーター。

*newValue*<br/>
新しい要素の値を指定します。

### <a name="remarks"></a>解説

まず、キーが検索されます。 キーが見つかった場合は、対応する値が変更されます。それ以外の場合は、新しいキーと値のペアが作成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
