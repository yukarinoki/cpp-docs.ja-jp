---
description: '詳細情報: CMapStringToOb クラス'
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
ms.openlocfilehash: 9bd5f47fbb85e67784e5bcb50029d9d9e48e5bb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207866"
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
|[CMapStringToOb:: CMapStringToOb](#cmapstringtoob)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMapStringToOb:: GetCount](#getcount)|このマップ内の要素の数を返します。|
|[CMapStringToOb:: GetHashTableSize](#gethashtablesize)|ハッシュテーブル内の現在の要素数を確認します。|
|[CMapStringToOb:: GetNextAssoc](#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CMapStringToOb:: GetSize](#getsize)|このマップ内の要素の数を返します。|
|[CMapStringToOb:: GetStartPosition](#getstartposition)|最初の要素の位置を返します。|
|[CMapStringToOb:: HashKey](#hashkey)|指定したキーのハッシュ値を計算します。|
|[CMapStringToOb:: InitHashTable](#inithashtable)|ハッシュテーブルを初期化します。|
|[CMapStringToOb:: IsEmpty](#isempty)|空のマップ条件 (要素なし) があるかどうかをテストします。|
|[CMapStringToOb:: Lookup](#lookup)|Void ポインターキーに基づいて void ポインターを検索します。 ポインター値は、それが指すエンティティではなく、キー比較に使用されます。|
|[CMapStringToOb:: LookupKey](#lookupkey)|指定されたキー値に関連付けられているキーへの参照を返します。|
|[CMapStringToOb:: RemoveAll](#removeall)|このマップからすべての要素を削除します。|
|[CMapStringToOb:: RemoveKey](#removekey)|キーによって指定された要素を削除します。|
|[CMapStringToOb:: SetAt](#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CMapStringToOb:: operator \[\]](#operator_at)|Map に要素を挿入します。に対する演算子の代入 `SetAt` 。|

## <a name="remarks"></a>解説

`CString` -  `CObject*` マップにペア (要素) を挿入すると、キーとして文字列または値を使用して、ペアを効率的に取得または削除でき `CString` ます。 また、マップ内のすべての要素を反復処理することもできます。

POSITION 型の変数は、すべてのマップバリエーションの代替エントリアクセスに使用されます。 位置を使用して、エントリを "記憶" し、マップを反復処理することができます。 このイテレーションはキー値によって連続していると思われるかもしれません。そうじゃないです。 取得された要素のシーケンスは不確定です。

`CMapStringToOb` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素は、マップがアーカイブに格納されている場合は、オーバーロードされた挿入 ( **<<** ) 演算子またはメンバー関数と共にシリアル化され `Serialize` ます。

マップ内の個々の要素 (値と内容) の診断ダンプが必要な場合は、 `CString` `CObject` ダンプコンテキストの深さを1以上に設定する必要があります。

`CMapStringToOb`オブジェクトが削除されるか、その要素が削除されると、 `CString` オブジェクトと `CObject` ポインターが削除されます。 ポインターによって参照 `CObject` されているオブジェクトは破棄されません。

マップクラスの派生は、リストの派生に似ています。 特別な目的のリストクラスの派生の図解については、「 [コレクション](../../mfc/collections.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>要件

**ヘッダー:** afxcoll.h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a> CMapStringToOb:: CMapStringToOb

空 `CString` のマップを構築 `CObject*` します。

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
マップを拡張するためのメモリ割り当ての粒度を指定します。

### <a name="remarks"></a>解説

マップが大きくなるにつれて、メモリは *Nblocksize* エントリの単位で割り当てられます。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb:: CMapStringToOb` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a> CMapStringToOb:: GetCount

マップ内の要素の数を決定します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

このマップ内の要素の数。

### <a name="remarks"></a>解説

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::GetCount` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a> CMapStringToOb:: GetHashTableSize

ハッシュテーブル内の現在の要素数を確認します。

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>戻り値

ハッシュテーブル内の要素の数を返します。

### <a name="remarks"></a>解説

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::GetHashTableSize` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a> CMapStringToOb:: GetNextAssoc

*Rnextposition* にマップ要素を取得し、 *rnextposition* を更新してマップ内の次の要素を参照します。

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>パラメーター

*rNextPosition*<br/>
前のまたは呼び出しによって返される位置値への参照を指定し `GetNextAssoc` `GetStartPosition` ます。

*rKey*<br/>
取得した要素の返されたキー (文字列) を指定します。

*右辺値*<br/>
取得した要素 (ポインター) の戻り値を指定し `CObject` ます。 このパラメーターの詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も役立ちます。 位置シーケンスは必ずしもキー値のシーケンスと同じではないことに注意してください。

取得した要素が map 内の最後の要素である場合、 *Rnextposition* の新しい値は NULL に設定されます。

*右辺* 値パラメーターの場合は、次の例に示すように、オブジェクトの型を **CObject \* &** にキャストします。これはコンパイラが必要とするものです。

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

これは、 `GetNextAssoc` テンプレートに基づくマップの場合には当てはまりません。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::GetNextAssoc` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (POSITION&** *rnextposition* **、void \* &** *rkey* **、void \* &** *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (POSITION&** *rnextposition* **、void \* &** *rkey* **、WORD&** *右辺* 値 **) const。**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (POSITION&** *rnextposition* **、CString&** *rkey* **、void \* &** *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Void GetNextAssoc (POSITION&** *rnextposition* **、cstring&** *rkey* **、cstring&** *右辺* 値 **) const。**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (POSITION&** *rnextposition* **、WORD&** *rkey* **、CObject \* &** *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (POSITION&** *rnextposition* **、WORD&** *rkey* **、void \* &** *rValue* **) const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

このプログラムの結果は次のとおりです。

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a> CMapStringToOb:: GetSize

マップ要素の数を返します。

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>戻り値

マップ内のアイテムの数。

### <a name="remarks"></a>解説

Map 内の要素の数を取得するには、このメソッドを呼び出します。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::GetSize` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a> CMapStringToOb:: GetStartPosition

呼び出しに渡すことができる位置の値を返すことによって、マップの反復処理を開始し `GetNextAssoc` ます。

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>戻り値

マップの反復処理の開始位置を示す位置の値です。または、マップが空の場合は NULL になります。

### <a name="remarks"></a>解説

イテレーションシーケンスは予測できません。したがって、"map 内の最初の要素" には特別な意味はありません。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::GetStartPosition` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition () const;**|

### <a name="example"></a>例

[CMapStringToOb:: GetNextAssoc](#getnextassoc)の例を参照してください。

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a> CMapStringToOb:: HashKey

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

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::HashKey` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void** <strong>\*</strong> `key`**) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void** <strong>\*</strong> `key`**) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT hashkey (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT hashkey (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT hashkey (WORD** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT hashkey (WORD** `key` **) const;**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a> CMapStringToOb:: InitHashTable

ハッシュテーブルを初期化します。

```cpp
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>パラメーター

*hashSize*<br/>
ハッシュテーブル内のエントリの数。

*今すぐ*<br/>
TRUE の場合、初期化時にハッシュテーブルを割り当てます。それ以外の場合は、必要に応じてテーブルが割り当てられます。

### <a name="remarks"></a>解説

最適なパフォーマンスを得るには、ハッシュテーブルのサイズを素数にする必要があります。 競合を最小限に抑えるには、予想される最大のデータセットよりもサイズを約20% 大きくする必要があります。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::InitHashTable` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a> CMapStringToOb:: IsEmpty

マップが空かどうかを判断します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

このマップに要素が含まれていない場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[RemoveAll](#removeall)の例を参照してください。

### <a name="remarks"></a>解説

次の表は、 **CMapStringToOb:: IsEmpty** に似た他のメンバー関数を示しています。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a> CMapStringToOb:: Lookup

`CObject`値に基づいてポインターを返し `CString` ます。

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別する文字列キーを指定します。

*右辺値*<br/>
検索された要素から返された値を指定します。

### <a name="return-value"></a>戻り値

要素が見つかった場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

`Lookup` ハッシュアルゴリズムを使用して、正確な (値) に一致するキーを持つ map 要素をすばやく検索し `CString` ます。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::LookUp` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Lookup (void** <strong>\*</strong> `key`**、void \* &**`rValue` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Lookup (void** <strong>\*</strong> `key`**, WORD&** `rValue`**) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Lookup (LPCTSTR** `key` **, void \* &** `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL Lookup (LPCTSTR** `key` **, CString&** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Lookup (WORD** `key` **, CObject \* &** `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Lookup (WORD** `key` **, void \* &** `rValue` **) const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a> CMapStringToOb:: LookupKey

指定されたキー値に関連付けられているキーへの参照を返します。

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索する要素を識別する文字列キーを指定します。

*rKey*<br/>
関連付けられているキーへの参照。

### <a name="return-value"></a>戻り値

キーが見つかった場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

関連付けられた要素がマップから削除された後、またはマップが破棄された後に使用された場合、キーへの参照を使用することは安全ではありません。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb:: LookupKey` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL lookupkey (LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL lookupkey (LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a> CMapStringToOb:: operator []

メンバー関数の便利な代替手段 `SetAt` 。

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>戻り値

オブジェクトへのポインターへの参照 `CObject` 。または、マップが空であるか、 *キー* が範囲外の場合は NULL。

### <a name="remarks"></a>解説

したがって、代入ステートメント (左辺値) の左側でのみ使用できます。 指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。

マップ内にキーが見つからない可能性があるため、この演算子に相当する "右辺" (r 値) はありません。 `Lookup`要素の取得には、メンバー関数を使用します。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::operator []` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void \*& operator \[ ] (void \*</strong> `key` **\) )**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD& 演算子 \[ ](void** <strong>\*</strong>`key` **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void \*& operator \[ ] (lpctstr** `key` **\) ;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString& operator \[ ](lpctstr** `key`**\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject \*& operator \[ ] (word** `key` **\) ;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void \*& operator \[ ] (word** `key` **\) ;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

このプログラムの結果は次のとおりです。

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a> CMapStringToOb:: RemoveAll

このマップからすべての要素を削除し、 `CString` キーオブジェクトを破棄します。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

`CObject`各キーによって参照されるオブジェクトは破棄されません。 参照された `RemoveAll` オブジェクトが確実に破棄されない場合、関数はメモリリークを発生させる可能性があり `CObject` ます。

マップが既に空の場合、関数は正しく動作します。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::RemoveAll` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a> CMapStringToOb:: RemoveKey

指定されたキーに対応するマップエントリを検索します。次に、キーが見つかった場合は、エントリを削除します。

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
マップの参照に使用する文字列を指定します。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

オブジェクトが他の場所で削除されていない場合、メモリリークが発生する可能性があり `CObject` ます。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::RemoveKey` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key`**);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key`**);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

このプログラムの結果は次のとおりです。

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a> CMapStringToOb:: SetAt

主な手段は、map に要素を挿入することです。

```cpp
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
新しい要素のキーである文字列を指定します。

*newValue*<br/>
`CObject`新しい要素の値であるポインターを指定します。

### <a name="remarks"></a>解説

まず、キーが検索されます。 キーが見つかった場合は、対応する値が変更されます。それ以外の場合は、新しいキーと値の要素が作成されます。

次の表は、に似た他のメンバー関数を示して `CMapStringToOb::SetAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Void SetAt (void)** <strong>\*</strong> `key`**、void** <strong>\*</strong>`newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Void SetAt (void)** <strong>\*</strong> `key`**, WORD** `newValue`**);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

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

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[CMapStringToString クラス](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb クラス](../../mfc/reference/cmapwordtoob-class.md)<br/>
[CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)
