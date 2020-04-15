---
title: CMapStringToOb クラス
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: 12de7bd72f643f08cebf948634703172d6725ce6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370102"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb クラス

一意の `CString` オブジェクトを `CObject` へのポインターに割り当てる辞書コレクション クラスです。

## <a name="syntax"></a>構文

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[トオブ::Cマップ文字列トーブ](#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[トオブ::取得カウント](#getcount)|このマップ内の要素の数を返します。|
|[をクリックします。](#gethashtablesize)|ハッシュ テーブル内の現在の要素数を決定します。|
|[トオブ::ゲットネクストアソック](#getnextassoc)|反復処理の次の要素を取得します。|
|[次の値を取得します。](#getsize)|このマップ内の要素の数を返します。|
|[次の値を取得します。](#getstartposition)|最初の要素の位置を返します。|
|[トオブ::ハッシュキー](#hashkey)|指定したキーのハッシュ値を計算します。|
|[次の文字列を作成します。](#inithashtable)|ハッシュ テーブルを初期化します。|
|[次の値を取得します。](#isempty)|空のマップ条件 (要素なし) をテストします。|
|[次の項目を検索します。](#lookup)|void ポインター キーに基づいて void ポインターを参照します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[トオブ::ルックアップキー](#lookupkey)|指定したキー値に関連付けられたキーへの参照を返します。|
|[すべての値を削除します。](#removeall)|このマップからすべての要素を削除します。|
|[トオブ::キーの削除](#removekey)|キーで指定された要素を削除します。|
|[トオブ::セットアット](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[次の操作を行います。 \[\]](#operator_at)|要素をマップに挿入します 。 `SetAt`|

## <a name="remarks"></a>解説

マップにペア (要素`CString`- ) を挿入した後、文字列または値をキーとして使用して、ペアを`CString`効率的に取得または削除できます。 `CObject*` マップ内のすべての要素を反復処理することもできます。

POSITION タイプの変数は、すべてのマップ・バリエーションで代替エントリー・アクセスに使用されます。 POSITION を使用して、エントリを 「記憶」し、マップを反復処理できます。 この反復はキー値によって順次的に行われると思うかもしれません。そうじゃないです。 取得された要素のシーケンスは不確定です。

`CMapStringToOb` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 マップがアーカイブに格納されている場合、各**<<**`Serialize`要素は順番にシリアル化されます。

マップ内の個々の要素 (値と内容) の診断`CString`ダンプが`CObject`必要な場合は、ダンプ コンテキストの深さを 1 以上に設定する必要があります。

オブジェクトが`CMapStringToOb`削除されたとき、またはその要素が削除されると、`CString`オブジェクトと`CObject`ポインターは削除されます。 `CObject`ポインターによって参照されるオブジェクトは破棄されません。

マップ クラスの派生は、リストの派生に似ています。 特殊目的リスト クラスの派生の例については、記事[の「コレクション](../../mfc/collections.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a>トオブ::Cマップ文字列トーブ

空`CString`の -to-map`CObject*`を構築します。

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
マップを拡張するためのメモリ割り当ての粒度を指定します。

### <a name="remarks"></a>解説

マップが大きくなると、メモリは*nBlockSize*エントリの単位で割り当てられます。

次の表に、 に似たその他`CMapStringToOb:: CMapStringToOb`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR** `nBlockSize` **= 10)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**文字列をINT_PTR** `nBlockSize` **= 10;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**マップワードトープター(INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a>トオブ::取得カウント

マップ内の要素の数を決定します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

このマップ内の要素の数。

### <a name="remarks"></a>解説

次の表に、 に似たその他`CMapStringToOb::GetCount`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTRカウント( ) 定数。**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTRカウント( ) 定数。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTRカウント( ) 定数。**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTRカウント( ) 定数。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTRカウント( ) 定数。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTRカウント( ) 定数。**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a>をクリックします。

ハッシュ テーブル内の現在の要素数を決定します。

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>戻り値

ハッシュ テーブル内の要素の数を返します。

### <a name="remarks"></a>解説

次の表に、 に似たその他`CMapStringToOb::GetHashTableSize`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**を取得します。**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**を取得します。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**を取得します。**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**を取得します。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**を取得します。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**を取得します。**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a>トオブ::ゲットネクストアソック

*で*マップ要素を取得し、マップ内の次の要素を参照するように*rNextPosition*を更新します。

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>パラメーター

*次の位置*<br/>
前`GetNextAssoc`の呼び出しまたは`GetStartPosition`呼び出しによって返される POSITION 値への参照を指定します。

*rキー*<br/>
取得した要素の返されたキー (文字列) を指定します。

*Rvalue*<br/>
取得した要素の戻り値 (ポインター)`CObject`を指定します。 このパラメータの詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も便利です。 位置順序は、必ずしもキー値シーケンスと同じではありません。

取得した要素がマップ内の最後の要素である場合 *、rNextPosition*の新しい値は NULL に設定されます。

*rValue*パラメーターの場合は、次の例に示すように、コンパイラが必要とする**CObject\*** にオブジェクト型をキャストしてください。

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

これは、テンプレートに基`GetNextAssoc`づくマップには当てはまりません。

次の表に、 に似たその他`CMapStringToOb::GetNextAssoc`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**無効なGetNextAssoc(位置***&rNextPosition、***\*ボイド***rKey、***ボイド\****rValue)***の定数;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**無効なGetNextAssoc(位置***&rNextPosition* **\* 、ボイド***rKey* **、WORD&** *rValue)***の定数;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**無効なGetNextAssoc(位置***&rNextPosition、C***文字列&** *rKey、***ボイド\****rValue)***の定数。**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**無効なGetNextAssoc(位置***&rNextPosition、C***文字列***&rKey* **、C文字列&** *rValue)***の定数。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**無効なGetNextAssoc( 位置&** *rNextPosition* **, 単語&** *rKey* **, CObject\* ** *rValue* **)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**無効なGetNextAssoc(位置***&rNextPosition,***ワード***&rKey、***ボイド\****rValue)***の定数;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

このプログラムの結果は次のとおりです。

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a>次の値を取得します。

マップ要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

マップ内のアイテムの数。

### <a name="remarks"></a>解説

マップ内の要素の数を取得します。

次の表に、 に似たその他`CMapStringToOb::GetSize`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTRします。**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTRします。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTRします。**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTRします。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTRします。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTRします。**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a>次の値を取得します。

呼び出しに渡すことができる POSITION 値を返すことによって、`GetNextAssoc`マップの反復処理を開始します。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップを反復処理するための開始位置を示す POSITION 値。マップが空の場合は NULL。

### <a name="remarks"></a>解説

反復シーケンスは予測できません。したがって、「マップの最初の要素」には特別な意味はありません。

次の表に、 に似たその他`CMapStringToOb::GetStartPosition`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**位置取得位置( ) 定数。**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**位置取得位置( ) 定数。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**位置取得位置( ) 定数。**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**位置取得位置( ) 定数。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**位置取得位置( ) 定数。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**位置取得位置( ) 定数。**|

### <a name="example"></a>例

[の](#getnextassoc)例を参照してください。

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a>トオブ::ハッシュキー

指定したキーのハッシュ値を計算します。

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
ハッシュ値を計算するキー。

### <a name="return-value"></a>戻り値

キーのハッシュ値

### <a name="remarks"></a>解説

次の表に、 に似たその他`CMapStringToOb::HashKey`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT ハッシュキー ( void** <strong>\*</strong> `key` **) 定数;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT ハッシュキー ( void** <strong>\*</strong> `key` **) 定数;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**コンストを指定**`key`**します。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**コンストを指定**`key`**します。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT ハッシュキー ( WORD** `key` **) の定数。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT ハッシュキー ( WORD** `key` **) の定数。**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a>次の文字列を作成します。

ハッシュ テーブルを初期化します。

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>パラメーター

*ハッシュサイズ*<br/>
ハッシュ テーブルのエントリ数。

*バロックナウ*<br/>
TRUE の場合は、初期化時にハッシュ テーブルを割り当てます。それ以外の場合は、必要に応じてテーブルが割り当てられます。

### <a name="remarks"></a>解説

最高のパフォーマンスを得る場合は、ハッシュ テーブルのサイズを素数にする必要があります。 衝突を最小限に抑えるには、サイズが予想される最大のデータセットよりも約 20% 大きい必要があります。

次の表に、 に似たその他`CMapStringToOb::InitHashTable`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**無効なイニトハッシュテーブル(UINT、**`hashSize`**ブール**`bAllocNow` **= 真);**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a>次の値を取得します。

マップが空かどうかを判断します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このマップに要素が含まれなかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

[「RemoveAll」](#removeall)の例を参照してください。

### <a name="remarks"></a>解説

次の表に **、CMapStringToOb:: IsEmpty**に似た他のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**ブールは空です( ) 定数;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**ブールは空です( ) 定数;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブールは空です( ) 定数;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**ブールは空です( ) 定数;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**ブールは空です( ) 定数;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**ブールは空です( ) 定数;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a>次の項目を検索します。

値に`CObject`基づいてポインターを`CString`返します。

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別する文字列キーを指定します。

*Rvalue*<br/>
検索された要素から返される値を指定します。

### <a name="return-value"></a>戻り値

要素が見つかった場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

`Lookup`ハッシュ アルゴリズムを使用して、正確に一致するキー (値)`CString`を持つマップ要素をすばやく見つけることができます。

次の表に、 に似たその他`CMapStringToOb::LookUp`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**ブールルックアップ(ボイド**<strong>\*</strong>`key`**、ボイド\***`rValue`**)の定数;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**ブールルックアップ(無効**<strong>\*</strong>`key`**、WORD** `rValue` **&)の定数。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブールルックアップ( LPCTSTR** `key` **,\* void** `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**ブールルックアップ( LPCTSTR** `key` **, C文字列&** `rValue` **) コンスト;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**ブールルックアップ(WORD、CObject)**`key`**\***`rValue`**の定数。**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**ブールルックアップ(WORD、**`key`**ボイド\***`rValue`**)の定数;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a>トオブ::ルックアップキー

指定したキー値に関連付けられたキーへの参照を返します。

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別する文字列キーを指定します。

*rキー*<br/>
関連付けられたキーへの参照。

### <a name="return-value"></a>戻り値

キーが見つかった場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

関連付けられた要素がマップから削除された後、またはマップが破棄された後に使用した場合、キーへの参照を使用することは安全ではありません。

次の表に、 に似たその他`CMapStringToOb:: LookupKey`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブール ルックアップ キー ( LPCTSTR** `key` **, LPCTSTR&** `rKey` **)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**ブール ルックアップ キー ( LPCTSTR** `key` **, LPCTSTR&** `rKey` **)**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a>次の値を指定します。

`SetAt`メンバー関数の代わりに便利です。

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>戻り値

`CObject`オブジェクトへのポインターへの参照。マップが空の場合、または*キー*が範囲外の場合は NULL。

### <a name="remarks"></a>解説

したがって、代入ステートメントの左側 (左辺値) でのみ使用できます。 指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。

マップ内にキーが見つからない可能性があるため、この演算子と同等の"右辺"(r値)はありません。 要素を`Lookup`取得するには、メンバー関数を使用します。

次の表に、 に似たその他`CMapStringToOb::operator []`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>無効\*&演算子\[ \* [(void;</strong> `key` ** \)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD&\[演算子 [](void** <strong>\*</strong> `key` ** \);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*&\[演算子 [(lpctstr;** `key` ** \)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**C文字列&演算子\[](lpctstr;** `key` ** \)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*&\[演算子 ](単語**`key`**\);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**無効\*&演算子\[](単語**`key`**\);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

このプログラムの結果は次のとおりです。

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a>すべての値を削除します。

このマップからすべての要素を削除し、キー オブジェクト`CString`を破棄します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

各`CObject`キーによって参照されるオブジェクトは破棄されません。 参照`RemoveAll``CObject`先オブジェクトが確実に破棄されない場合、この関数はメモリ リークを引き起こす可能性があります。

マップが既に空の場合、関数は正しく動作します。

次の表に、 に似たその他`CMapStringToOb::RemoveAll`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**無効すべてを削除します( );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**無効すべてを削除します( );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**無効すべてを削除します( );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**無効すべてを削除します( );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**無効すべてを削除します( );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**無効すべてを削除します( );**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a>トオブ::キーの削除

指定されたキーに対応するマップ エントリを調えます。キーが見つかった場合は、エントリを削除します。

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
マップ検索に使用する文字列を指定します。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトが他の場所で`CObject`削除されていない場合、メモリ リークが発生する可能性があります。

次の表に、 に似たその他`CMapStringToOb::RemoveKey`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL除去キー(ボイド**<strong>\*</strong>`key`**);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL除去キー(ボイド**<strong>\*</strong>`key`**);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブール除去キー ( LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**ブール除去キー ( LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**ブール除去キー(WORD);** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**ブール除去キー(WORD);** `key` **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

このプログラムの結果は次のとおりです。

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a>トオブ::セットアット

マップに要素を挿入する主な手段。

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
新しい要素のキーである文字列を指定します。

*newValue*<br/>
新しい`CObject`要素の値であるポインターを指定します。

### <a name="remarks"></a>解説

まず、キーを検索します。 キーが見つかった場合は、対応する値が変更されます。それ以外の場合は、新しいキー値要素が作成されます。

次の表に、 に似たその他`CMapStringToOb::SetAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**無効設定(ボイド**<strong>\*</strong>`key`**、ボイド**<strong>\*</strong>`newValue`**);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**ボイドセットアット(ボイド**<strong>\*</strong>`key`**、WORD);** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ボイドセットアット(LPCTSTR、**`key`**ボイド**<strong>\*</strong>`newValue`**);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**無効なセットアット( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**無効セットアット(WORD、C**`key`**オブジェクト**<strong>\*</strong>`newValue`**);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**無効セットアット(WORD、**`key`**ボイド**<strong>\*</strong>`newValue`**);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

このプログラムの結果は次のとおりです。

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)<br/>
[クラスを作成します。](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[CMapStringToString クラス](../../mfc/reference/cmapstringtostring-class.md)<br/>
[クラス](../../mfc/reference/cmapwordtoob-class.md)<br/>
[クラスを使用します。](../../mfc/reference/cmapwordtoptr-class.md)
