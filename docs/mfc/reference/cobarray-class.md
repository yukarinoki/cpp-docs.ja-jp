---
title: CObArray クラス
ms.date: 11/04/2016
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
ms.openlocfilehash: b083bf0e82f9d9b928e613f07a71d36147240cd2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212372"
---
# <a name="cobarray-class"></a>CObArray クラス

`CObject` ポインターの配列をサポートします。

## <a name="syntax"></a>構文

```
class CObArray : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CObArray:: CObArray](#cobarray)|ポインターの空の配列を構築 `CObject` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CObArray:: Add](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[CObArray:: Append](#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[CObArray:: Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[CObArray:: ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[CObArray:: FreeExtra](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[CObArray:: GetAt](#getat)|指定されたインデックス位置にある値を返します。|
|[CObArray:: GetCount](#getcount)|この配列内の要素の数を取得します。|
|[CObArray:: GetData](#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[CObArray:: GetSize](#getsize)|この配列内の要素の数を取得します。|
|[CObArray:: System.array.getupperbound](#getupperbound)|有効な最大のインデックスを返します。|
|[CObArray:: InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[CObArray:: IsEmpty](#isempty)|配列が空かどうかを判別します。|
|[CObArray:: RemoveAll](#removeall)|この配列からすべての要素を削除します。|
|[CObArray:: RemoveAt](#removeat)|特定のインデックス位置にある要素を削除します。|
|[CObArray:: SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[CObArray:: SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[CObArray:: SetSize](#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CObArray:: operator \[\]](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

これらのオブジェクト配列は C 配列に似ていますが、必要に応じて動的に縮小したり拡張したりすることができます。

配列インデックスは、常に0の位置から開始します。 現在のバインドされている要素を追加するときに、上限を修正するか、配列の拡張を許可するかを決定できます。 一部の要素が null であっても、メモリは上限に連続して割り当てられます。

Win32 では、オブジェクトのサイズ `CObArray` は使用可能なメモリに限定されます。

C 配列の場合と同様に、インデックス付き要素のアクセス時間は定数であり、 `CObArray` 配列のサイズに依存しません。

`CObArray`には、要素のシリアル化とダンプをサポートするために IMPLEMENT_SERIAL マクロが組み込まれています。 ポインターの配列 `CObject` が、オーバーロードされた挿入演算子またはメンバー関数を使用してアーカイブに格納されている場合、 `Serialize` 各 `CObject` 要素は配列インデックスと共にシリアル化されます。

配列内の個々の要素のダンプが必要な場合は、 `CObject` オブジェクトの深さ `CDumpContext` を1以上に設定する必要があります。

オブジェクトが削除されたとき `CObArray` 、またはその要素が削除されたときには、 `CObject` ポインターだけが削除されます。参照するオブジェクトは削除されません。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列クラスの派生は、リストの派生に似ています。 特別な目的のリストクラスの派生の詳細については、「[コレクション](../../mfc/collections.md)」を参照してください。

> [!NOTE]
> 配列をシリアル化する場合は、派生クラスの実装で IMPLEMENT_SERIAL マクロを使用する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="cobarrayadd"></a><a name="add"></a>CObArray:: Add

配列の末尾に新しい要素を追加し、配列を1だけ拡大します。

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*(Newelement*<br/>
`CObject`この配列に追加するポインター。

### <a name="return-value"></a>戻り値

追加された要素のインデックス。

### <a name="remarks"></a>解説

値が1より大きい*Ngrowby* [SetSize](#setsize)が使用されている場合は、余分なメモリが割り当てられることがあります。 ただし、上限は1だけ増加します。

次の表は、に似た他のメンバー関数を示して `CObArray::Add` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR 追加 (BYTE** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR 追加 (DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR 追加 (void)** <strong>\*</strong> `newElement`**);**<br /><br /> **throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Add (LPCTSTR** `newElement` **); throw (CMemoryException \* );**<br /><br /> **INT_PTR Add (Const CString&** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR 加算 (UINT** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 追加 (WORD** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

このプログラムの結果は次のとおりです。

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>CObArray:: Append

このメンバー関数を呼び出して、指定した配列の末尾に別の配列の内容を追加します。

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
配列に追加する要素のソース。

### <a name="return-value"></a>戻り値

追加された最初の要素のインデックス。

### <a name="remarks"></a>解説

配列は同じ型である必要があります。

必要に応じ `Append` て、は配列に追加された要素を格納するために追加のメモリを割り当てることができます。

次の表は、に似た他のメンバー関数を示して `CObArray::Append` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Append (Const CByteArray&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Append (Const CDWordArray&** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Append (Const CPtrArray&** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Append (Const CStringArray&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Append (Const CUIntArray&** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR 追加 (Const CWordArray&** *src* **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>CObArray:: Copy

指定した配列の要素を、同じ型の別の配列の要素で上書きするには、このメンバー関数を呼び出します。

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
配列にコピーされる要素のソース。

### <a name="remarks"></a>解説

`Copy`はメモリを解放しません。ただし、必要に応じ `Copy` て、は配列にコピーされた要素を格納するために追加のメモリを割り当てることがあります。

次の表は、に似た他のメンバー関数を示して `CObArray::Copy` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Void コピー (Const CByteArray&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Void コピー (Const CDWordArray&** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Void コピー (Const CPtrArray&** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Void Copy (Const CStringArray&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Void コピー (Const CUIntArray&** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Void Copy (Const CWordArray&** *src* **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>CObArray:: CObArray

空 `CObject` のポインター配列を構築します。

```
CObArray();
```

### <a name="remarks"></a>解説

配列は、一度に1つの要素を拡張します。

次の表は、に似た他のコンストラクターを示して `CObArray::CObArray` います。

|クラス|コンストラクター|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>CObArray:: ElementAt

配列内の要素ポインターへの一時的な参照を返します。

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上で、によって返された値以下の整数のインデックス `GetUpperBound` 。

### <a name="return-value"></a>戻り値

ポインターへの参照 `CObject` 。

### <a name="remarks"></a>解説

これは、配列の左側の代入演算子を実装するために使用されます。 これは、特別な配列演算子を実装するためにのみ使用する必要がある高度な関数です。

次の表は、に似た他のメンバー関数を示して `CObArray::ElementAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト& ElementAt (INT_PTR** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& ElementAt (INT_PTR** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \*& elementat (INT_PTR** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& ElementAt (INT_PTR** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& ElementAt (INT_PTR** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& ElementAt (INT_PTR** `nIndex` **);**|

### <a name="example"></a>例

  [CObArray:: GetSize](#getsize)の例を参照してください。

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>CObArray:: FreeExtra

配列が拡張されたときに割り当てられた余分なメモリを解放します。

```cpp
void FreeExtra();
```

### <a name="remarks"></a>解説

この関数は、配列のサイズや上限には影響しません。

次の表は、に似た他のメンバー関数を示して `CObArray::FreeExtra` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra ();**|

### <a name="example"></a>例

  [CObArray:: GetData](#getdata)の例を参照してください。

## <a name="cobarraygetat"></a><a name="getat"></a>CObArray:: GetAt

指定したインデックス位置にある配列要素を返します。

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上で、によって返された値以下の整数のインデックス `GetUpperBound` 。

### <a name="return-value"></a>戻り値

`CObject`現在このインデックスにあるポインター要素。

### <a name="remarks"></a>解説

> [!NOTE]
> 負の値またはから返された値より大きい値を渡す `GetUpperBound` と、アサーションは失敗します。

次の表は、に似た他のメンバー関数を示して `CObArray::GetAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE GetAt (INT_PTR** `nIndex` **) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \*GetAt (INT_PTR** `nIndex` **) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>CObArray:: GetCount

配列要素の数を返します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

配列内の項目の数。

### <a name="remarks"></a>解説

配列内の要素の数を取得するには、このメソッドを呼び出します。 インデックスは0から始まるため、サイズは最大のインデックスよりも1大きい値になります。

次の表は、に似た他のメンバー関数を示して `CObArray::GetCount` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>CObArray:: GetData

このメンバー関数を使用して、配列内の要素への直接アクセスを取得します。

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>戻り値

ポインターの配列へのポインター `CObject` 。

### <a name="remarks"></a>解説

使用可能な要素がない場合、は `GetData` null 値を返します。

配列の要素に直接アクセスして、より迅速に作業を行うことができますが、を呼び出すときは注意が必要です。これにより、 `GetData` 配列の要素に直接影響を与えるエラーが発生します。

次の表は、に似た他のメンバー関数を示して `CObArray::GetData` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const BYTE \* GetData () const;バイト \* GetData ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD \* getdata () const; DWORD \* getdata ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void \* \* getdata () const; void \* \* getdata ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString \* GetData () const;CString \* ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT \* GetData () const;UINT \* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD \* GetData () const;WORD \* GetData ();**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>CObArray:: GetSize

配列のサイズを返します。

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>解説

インデックスは0から始まるため、サイズは最大のインデックスよりも1大きい値になります。

次の表は、に似た他のメンバー関数を示して `CObArray::GetSize` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>CObArray:: System.array.getupperbound

この配列の現在の上限を返します。

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>戻り値

上限のインデックス (0 から始まる)。

### <a name="remarks"></a>解説

配列インデックスは0から始まるため、この関数はより小さい値1を返し `GetSize` ます。

条件 `GetUpperBound( )` =-1 は、配列に要素が含まれていないことを示します。

次の表は、に似た他のメンバー関数を示して `CObArray::GetUpperBound` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR System.array.getupperbound () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR System.array.getupperbound () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR System.array.getupperbound () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR System.array.getupperbound () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR System.array.getupperbound () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR System.array.getupperbound () const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>CObArray:: InsertAt

指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。

```cpp
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
によって返される値よりも大きい可能性のある整数インデックス `GetUpperBound` 。

*(Newelement*<br/>
`CObject`この配列に配置するポインター。 値が NULL の*Newelement*は使用できます。

*nCount*<br/>
この要素を挿入する回数 (既定値は 1)。

*nStartIndex*<br/>
によって返される値よりも大きい可能性のある整数インデックス `GetUpperBound` 。

*pNewArray*<br/>
この配列に追加する要素を格納している別の配列。

### <a name="remarks"></a>解説

の最初のバージョンで `InsertAt` は、配列内の指定したインデックス位置に1つの要素 (または要素の複数のコピー) を挿入します。 このプロセスでは、このインデックスの既存の要素を (インデックスのインクリメントによって) シフトアップし、その上にあるすべての要素をシフトアップします。

2番目のバージョンでは、Nstartindex 位置から開始して、別のコレクションのすべての要素を挿入し `CObArray` ます。 *nStartIndex*

これに対し、関数は、 `SetAt` 指定された1つの配列要素を置き換え、要素をシフトしません。

次の表は、に似た他のメンバー関数を示して `CObArray::InsertAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, BYTE** `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, cdwordarray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, cstringarray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, UINT** `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, cuintarray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, INT** `nCount` **= 1);**<br /><br /> **throw (CMemoryException \* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, cwordarray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException \* );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>CObArray:: IsEmpty

配列が空かどうかを判別します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

配列が空の場合は0以外の。それ以外の場合は0です。

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>CObArray:: operator []

これらの添字演算子は、関数と関数に代わる便利な方法 `SetAt` `GetAt` です。

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>解説

ではない配列に対して呼び出される最初の演算子は、 **`const`** 代入ステートメントの right (右辺値) または left (左辺値) のいずれかで使用できます。 配列に対して呼び出される2番目のは、 **`const`** 右側でのみ使用できます。

ライブラリのデバッグバージョンは、添字 (代入ステートメントの左側または右側) が範囲外である場合にアサートします。

次の表は、に似た他の演算子を示して `CObArray::operator []` います。

|クラス|演算子|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **BYTE 演算子 [] (int_ptr** `nindex` ** \) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **DWORD 演算子 [] (int_ptr** `nindex` ** \) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \*& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **void \* operator [] (int_ptr** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **CString 演算子 [] (int_ptr** `nindex` ** \) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **UINT 演算子 [] (int_ptr** `nindex` ** \) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& operator [] (int_ptr** `nindex` ** \) ;**<br /><br /> **WORD operator [] (int_ptr** `nindex` ** \) const;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>CObArray:: RemoveAll

この配列からすべてのポインターを削除しますが、実際にはオブジェクトを削除しません `CObject` 。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>解説

配列が既に空の場合、関数は引き続き機能します。

関数は、 `RemoveAll` ポインターストレージに使用されるすべてのメモリを解放します。

次の表は、に似た他のメンバー関数を示して `CObArray::RemoveAll` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll ();**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>CObArray:: RemoveAt

配列内の指定したインデックスを開始位置として、1つ以上の要素を削除します。

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上で、によって返された値以下の整数のインデックス `GetUpperBound` 。

*nCount*<br/>
削除する要素の数を指定します。

### <a name="remarks"></a>解説

プロセスでは、削除された要素の上にあるすべての要素を下へ移動します。 配列の上限をデクリメントしますが、メモリは解放されません。

削除ポイントの上の配列に含まれているよりも多くの要素を削除しようとすると、ライブラリのデバッグバージョンがアサートされます。

関数は、 `RemoveAt` `CObject` 配列からポインターを削除しますが、オブジェクト自体は削除しません。

次の表は、に似た他のメンバー関数を示して `CObArray::RemoveAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** `nCount` **= 1);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** `nCount` **= 1);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** `nCount` **= 1);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** `nCount` **= 1);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** `nCount` **= 1);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **、INT_PTR** *nCount* **= 1);**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

このプログラムの結果は次のとおりです。

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>CObArray:: SetAt

指定したインデックス位置に配列要素を設定します。

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上で、によって返された値以下の整数のインデックス `GetUpperBound` 。

*(Newelement*<br/>
この配列に挿入されるオブジェクトポインター。 NULL 値が許可されます。

### <a name="remarks"></a>解説

`SetAt`では、配列が拡張されることはありません。 `SetAtGrow`配列が自動的に拡張されるようにする場合は、を使用します。

インデックス値が配列内の有効な位置を表していることを確認する必要があります。 範囲外の場合は、ライブラリのデバッグバージョンがアサートされます。

次の表は、に似た他のメンバー関数を示して `CObArray::SetAt` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt (INT_PTR** `nIndex` **, BYTE** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, UINT** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, WORD** `newElement` **);**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>CObArray:: SetAtGrow

指定したインデックス位置に配列要素を設定します。

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上の整数のインデックスです。

*(Newelement*<br/>
この配列に追加するオブジェクトポインター。 NULL 値が許可されます。

### <a name="remarks"></a>解説

必要に応じて配列が自動的に拡張されます (つまり、新しい要素に合わせて上限が調整されます)。

次の表は、に似た他のメンバー関数を示して `CObArray::SetAtGrow` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, BYTE** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw (CMemoryException \* );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については、「 [coblist:: coblist](../../mfc/reference/coblist-class.md#coblist) 」を参照してください `CAge` 。

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>CObArray:: SetSize

空または既存の配列のサイズを設定します。必要に応じてメモリを割り当てます。

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>パラメーター

*nNewSize*<br/>
新しい配列のサイズ (要素の数)。 0 以上であることが必要です。

*nGrowBy*<br/>
サイズの増加が必要な場合に割り当てる要素スロットの最小数。

### <a name="remarks"></a>解説

新しいサイズが古いサイズより小さい場合は、配列が切り捨てられ、未使用のメモリがすべて解放されます。 効率を上げるために、を呼び出し `SetSize` て配列のサイズを設定してから使用します。 これにより、項目が追加されるたびに、配列を再割り当てしてコピーする必要がなくなります。

*Ngrowby*パラメーターは、配列が拡大している間の内部メモリの割り当てに影響します。 とによって報告された配列のサイズには影響しません `GetSize` `GetUpperBound` 。

配列のサイズが大きくなっている場合は、新しく割り当てられたすべての**CObject** <strong>\*</strong> ポインターが NULL に設定されます。

次の表は、に似た他のメンバー関数を示して `CObArray::SetSize` います。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, INT** `nGrowBy` **=-1);**<br /><br /> **throw (CMemoryException \* );**|

### <a name="example"></a>例

  [CObArray:: GetData](#getdata)の例を参照してください。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CStringArray クラス](../../mfc/reference/cstringarray-class.md)<br/>
[CPtrArray クラス](../../mfc/reference/cptrarray-class.md)<br/>
[CByteArray クラス](../../mfc/reference/cbytearray-class.md)<br/>
[CWordArray クラス](../../mfc/reference/cwordarray-class.md)<br/>
[CDWordArray クラス](../../mfc/reference/cdwordarray-class.md)
