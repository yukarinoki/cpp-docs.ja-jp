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
ms.openlocfilehash: 7b923fd9231d3652d8d2f1750a8024d15287811e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360444"
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
|[コブアレイ::コブアレイ](#cobarray)|ポインターの空の配列を`CObject`構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コブアレイ::追加](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[次の要素を追加します。](#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|
|[コブアレイ::コピー](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[コブアレイ::エレメントアット](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[コブアレイ::フリーエクストラ](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[コブアレイ::ゲットアット](#getat)|指定されたインデックス位置にある値を返します。|
|[コブアレイ::ゲットカウント](#getcount)|この配列内の要素の数を取得します。|
|[を取得します。](#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[コブアレイ::ゲットサイズ](#getsize)|この配列内の要素の数を取得します。|
|[コブアレイ::ゲットアッパーバウンド](#getupperbound)|有効な最大のインデックスを返します。|
|[コブアレイ::挿入](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[コブアレイ::IsEmpty](#isempty)|配列が空かどうかを判別します。|
|[すべてを削除します。](#removeall)|この配列からすべての要素を削除します。|
|[コブアレイ::削除アット](#removeat)|特定のインデックス位置にある要素を削除します。|
|[コブアレイ::セットアット](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[コブアレイ::セットアックグロー](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[::セットサイズ](#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コブアレイ::演算子\[\]](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

これらのオブジェクト配列は C 配列に似ていますが、必要に応じて動的に縮小および拡張できます。

配列インデックスは常に位置 0 から始まります。 現在の境界を超えて要素を追加するときに、上限を固定するか、配列を展開するかを決定できます。 一部の要素が null であっても、メモリは上限に連続して割り当てられます。

Win32 では、`CObArray`オブジェクトのサイズは使用可能なメモリのみに制限されます。

C 配列と同様に、`CObArray`インデックス付き要素のアクセス時間は一定であり、配列のサイズとは無関係です。

`CObArray`IMPLEMENT_SERIAL マクロを組み込んで、シリアル化と要素のダンプをサポートします。 ポインターの`CObject`配列が、オーバーロードされた挿入演算子または`Serialize`メンバー関数を使用してアーカイブに格納されている場合、各`CObject`要素は配列インデックスと共にシリアル化されます。

配列内の個々`CObject`の要素のダンプが必要な場合は、`CDumpContext`オブジェクトの深さを 1 以上に設定する必要があります。

オブジェクトが`CObArray`削除されたとき、またはその要素が削除されると、`CObject`ポインターだけが削除され、オブジェクトは削除されません。

> [!NOTE]
> 配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列クラスの派生は、リストの派生に似ています。 特殊目的リスト クラスの派生の詳細については、[記事のコレクションを](../../mfc/collections.md)参照してください。

> [!NOTE]
> 配列をシリアル化する場合は、派生クラスの実装で IMPLEMENT_SERIAL マクロを使用する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcoll.h

## <a name="cobarrayadd"></a><a name="add"></a>コブアレイ::追加

配列の末尾に新しい要素を追加し、配列を 1 ずつ増やします。

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*新しい要素*<br/>
この`CObject`配列に追加するポインター。

### <a name="return-value"></a>戻り値

追加された要素のインデックス。

### <a name="remarks"></a>解説

1 より大きい*nGrowBy*値を使用して[SetSize](#setsize)を使用している場合は、余分なメモリが割り当てられる可能性があります。 ただし、上限は 1 だけ増加します。

次の表に、 に似たその他`CObArray::Add`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR追加 ( バイト**`newElement` **) ;**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR追加( DWORD** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR追加(ボイド**<strong>\*</strong>`newElement`**);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR追加( LPCTSTR** `newElement` **); スロー\* ( C メモリ例外 );**<br /><br /> **INT_PTR追加(定数 C 文字列**`newElement`**&);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR追加( UINT** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR追加( WORD** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

このプログラムの結果は次のとおりです。

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>次の要素を追加します。

指定した配列の末尾に別の配列の内容を追加します。

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

必要に応`Append`じて、配列に追加された要素を格納するために余分なメモリを割り当てることができます。

次の表に、 に似たその他`CObArray::Append`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR追加( コンスト CByteArray&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR追加(コンストCDワードアレイ***&src);* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR追加( const CPtrArray&** *src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR追加( src )&コンスト CStringArray;** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR追加(const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR追加(コンストCWordArray&src);** *src* **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>コブアレイ::コピー

指定した配列の要素を、同じ型の別の配列の要素で上書きします。

```
void Copy(const CObArray& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
配列にコピーする要素のソース。

### <a name="remarks"></a>解説

`Copy`メモリを解放しません。ただし、必要に応`Copy`じて、配列にコピーされた要素を格納するために余分なメモリを割り当てる場合があります。

次の表に、 に似たその他`CObArray::Copy`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**ボイドコピー(コンストCバイトアレイ***&src);* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**ボイドコピー(コンストCDワードアレイ***&src);* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**ボイドコピー(コンストCPtrアレイ***&src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**ボイドコピー(const CStringArray&** *src);* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**ボイドコピー(const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ボイドコピー(const CWordArray&** *src);* **);**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>コブアレイ::コブアレイ

空`CObject`のポインター配列を構築します。

```
CObArray();
```

### <a name="remarks"></a>解説

配列は一度に 1 つの要素を増やします。

次の表に、 に似た他の`CObArray::CObArray`コンストラクターを示します。

|クラス|Constructor|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Cバイトアレイ( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CD-1;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrアレイ( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**C文字列配列( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**クイントアレイ( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Cワードアレイ( );**|

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>コブアレイ::エレメントアット

配列内の要素ポインターへの一時的な参照を返します。

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上、および によって返される`GetUpperBound`値以下の整数インデックス。

### <a name="return-value"></a>戻り値

`CObject`ポインターへの参照。

### <a name="remarks"></a>解説

配列の左辺代入演算子を実装するために使用されます。 これは、特殊な配列演算子を実装する場合にのみ使用する高度な関数であることに注意してください。

次の表に、 に似たその他`CObArray::ElementAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト&要素アット(INT_PTR)** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD&要素( INT_PTR** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**ボイド\*&要素アット(INT_PTR);** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**C弦&要素アット(INT_PTR);** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT&要素アット(INT_PTR);** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ワード&要素アット(INT_PTR);** `nIndex` **);**|

### <a name="example"></a>例

  [次](#getsize)の例を参照してください。

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>コブアレイ::フリーエクストラ

配列の拡大中に割り当てられた余分なメモリを解放します。

```
void FreeExtra();
```

### <a name="remarks"></a>解説

この関数は、配列のサイズや上限には影響しません。

次の表に、 に似たその他`CObArray::FreeExtra`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**ボイドフリーエクストラ( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**ボイドフリーエクストラ( );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**ボイドフリーエクストラ( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**ボイドフリーエクストラ( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**ボイドフリーエクストラ( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ボイドフリーエクストラ( );**|

### <a name="example"></a>例

  [の](#getdata)例を参照してください。

## <a name="cobarraygetat"></a><a name="getat"></a>コブアレイ::ゲットアット

指定したインデックス位置にある配列要素を返します。

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上、および によって返される`GetUpperBound`値以下の整数インデックス。

### <a name="return-value"></a>戻り値

現在`CObject`このインデックスにあるポインター要素。

### <a name="remarks"></a>解説

> [!NOTE]
> 負の値または返された値より大きい値を渡`GetUpperBound`すと、アサーションが失敗します。

次の表に、 に似たその他`CObArray::GetAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト GetAt( INT_PTR** `nIndex` **) の定数。**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt( INT_PTR** `nIndex` **) コンスト;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**無効\*な GetAt( INT_PTR** `nIndex` **) 定数。**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**定数を INT_PTR取得**`nIndex`します **。**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt( INT_PTR** `nIndex` **) コンスト;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**を INT_PTR**`nIndex`使用**します。**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>コブアレイ::ゲットカウント

配列要素の数を返します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

配列内の項目の数。

### <a name="remarks"></a>解説

配列内の要素の数を取得します。 インデックスは 0 から始まるので、サイズは最大のインデックスより 1 大きくなります。

次の表に、 に似たその他`CObArray::GetCount`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTRカウント( ) 定数。**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTRカウント( ) 定数。**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTRカウント( ) 定数。**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTRカウント( ) 定数。**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTRカウント( ) 定数。**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTRカウント( ) 定数。**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>を取得します。

このメンバー関数を使用して、配列内の要素に直接アクセスします。

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>戻り値

`CObject`ポインターの配列へのポインター。

### <a name="remarks"></a>解説

使用できる要素がない場合は`GetData`、null 値を返します。

配列の要素に直接アクセスすると作業の速度が向上しますが、呼び出す際`GetData`は注意が必要です。エラーが発生すると、配列の要素に直接影響します。

次の表に、 に似たその他`CObArray::GetData`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**定数バイト\*取得データ( ) 定数;バイト\*取得データ( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**を取得します\*\*。**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**を無効\*\*にします。\* \***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**定数 C\*文字列取得データ( ) 定数。C文字列\*取得データ( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**定数 UINT\* GetData( ) 定数。\*取得データの取得(**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**定数\*WORD 取得データ( ) 定数。ワード\*取得データ( );**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>コブアレイ::ゲットサイズ

配列のサイズを返します。

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>解説

インデックスは 0 から始まるので、サイズは最大のインデックスより 1 大きくなります。

次の表に、 に似たその他`CObArray::GetSize`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTRします。**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTRします。**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTRします。**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTRします。**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTRします。**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTRします。**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>コブアレイ::ゲットアッパーバウンド

この配列の現在の上限を返します。

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>戻り値

上限 (0 から始まる) のインデックス。

### <a name="remarks"></a>解説

配列インデックスは 0 から始まるので、この関数は 1`GetSize`より小さい値を返します。

条件`GetUpperBound( )`= -1 は、配列に要素が含まれていることを示します。

次の表に、 に似たその他`CObArray::GetUpperBound`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR大文字の行きとくれ( ) 定数。**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>コブアレイ::挿入

指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。

```
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
によって返される値より大きい場合がある整数インデックス`GetUpperBound`。

*新しい要素*<br/>
この`CObject`配列に配置されるポインター。 値 NULL の*新しい要素*が許可されます。

*nカウント*<br/>
この要素を挿入する回数 (既定値は 1)。

*インデックスを作成します。*<br/>
によって返される値より大きい場合がある整数インデックス`GetUpperBound`。

*をクリックします。*<br/>
この配列に追加する要素を含む別の配列。

### <a name="remarks"></a>解説

の最初のバージョン`InsertAt`では、配列内の指定したインデックスに 1 つの要素 (または要素の複数のコピー) が挿入されます。 このプロセスでは、このインデックスの既存の要素を (インデックスをインクリメントして) 上に移動し、その上にあるすべての要素を上に移動します。

2 番目のバージョンでは`CObArray`*、nStartIndex*の位置から、別のコレクションからすべての要素を挿入します。

これに`SetAt`対し、この関数は指定された配列要素を置き換え、要素をシフトしません。

次の表に、 に似たその他`CObArray::InsertAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, バイト**`newElement` **, int** `nCount` = **1);**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **void 挿入アット( INT_PTR** `nStartIndex` **, Cバイト配列**<strong>\*</strong>`pNewArray`**);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void 挿入( INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **空INSERTAt(INT_PTR** `nStartIndex` **、CDワードアレイ**<strong>\*</strong>`pNewArray`**);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1);**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **空INSERTAt( INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void 挿入(INT_PTR** `nIndex` **、 LPCTSTR** `newElement` **、int** `nCount` = **1);**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **空INSERTAt(INT_PTR、C**`nStartIndex`**弦配列**<strong>\*</strong>`pNewArray`**);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, UINT** `newElement` , **int** `nCount` **= 1);**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **void 挿入アット( INT_PTR** `nStartIndex` **, CUIntArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void 挿入(INT_PTR** `nIndex` **、 WORD** `newElement` **、 int** `nCount` **= 1 );**<br /><br /> **スロー( C\*メモリ例外 );**<br /><br /> **無効挿入(INT_PTR** `nStartIndex` **、CWordArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **スロー( C\*メモリ例外 );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

このプログラムの結果は次のとおりです。

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>コブアレイ::IsEmpty

配列が空かどうかを判別します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

配列が空の場合は 0 以外。それ以外の場合は 0。

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>コブアレイ::演算子 [ ]

これらの添字演算子は、`SetAt`と`GetAt`関数の代わりに便利です。

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>解説

**const**でない配列に対して呼び出される最初の演算子は、代入ステートメントの右 (r 値) または左 (左辺値) で使用できます。 **2**番目の定数配列は、右側でのみ使用できます。

ライブラリのデバッグ バージョンは、下付き文字 (代入ステートメントの左側または右側) が範囲外にある場合にアサートします。

次の表に、 に似た他`CObArray::operator []`の演算子を示します。

|クラス|演算子|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **BYTE 演算子 [](int_ptr**`nindex`**\)定数;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **DWORD 演算子 [](int_ptr** `nindex` ** \) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**無効\*&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **void\*演算子 [](int_ptr** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**C文字列&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **C文字列演算子 [](int_ptr**`nindex`**\)定数;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **UINT 演算子 [](int_ptr**`nindex`**\)定数;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ワード&演算子 [](int_ptr;** `nindex` ** \)**<br /><br /> **WORD 演算子 [](int_ptr**`nindex`**\)定数;**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>すべてを削除します。

この配列からすべてのポインターを削除しますが、実際にはオブジェクトは`CObject`削除しません。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

配列が既に空の場合でも、関数は動作します。

この`RemoveAll`関数は、ポインターの記憶に使用されるすべてのメモリを解放します。

次の表に、 に似たその他`CObArray::RemoveAll`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**無効すべてを削除します( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**無効すべてを削除します( );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**無効すべてを削除します( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**無効すべてを削除します( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**無効すべてを削除します( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**無効すべてを削除します( );**|

### <a name="example"></a>例

すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>コブアレイ::削除アット

配列内の指定したインデックス位置から開始する 1 つ以上の要素を削除します。

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上、および によって返される`GetUpperBound`値以下の整数インデックス。

*nカウント*<br/>
削除する要素の数を指定します。

### <a name="remarks"></a>解説

プロセスでは、削除された要素の上にあるすべての要素をシフトダウンします。 配列の上限を減らしますが、メモリは解放されません。

削除ポイントの上の配列に含まれている要素よりも多くの要素を削除しようとすると、ライブラリのデバッグ バージョンがアサートされます。

この`RemoveAt`関数は、ポインター`CObject`を配列から削除しますが、オブジェクト自体は削除しません。

次の表に、 に似たその他`CObArray::RemoveAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**ボイド除去(INT_PTR、INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**ボイド除去(INT_PTR、INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**ボイド除去(INT_PTR、INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**ボイド除去(INT_PTR、INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**ボイド除去(INT_PTR、INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void 削除( INT_PTR** `nIndex` **) INT_PTR** *nCount* **= 1);**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

このプログラムの結果は次のとおりです。

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>コブアレイ::セットアット

指定したインデックス位置に配列要素を設定します。

```
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上、および によって返される`GetUpperBound`値以下の整数インデックス。

*新しい要素*<br/>
この配列に挿入されるオブジェクト ポインター。 NULL 値を使用できます。

### <a name="remarks"></a>解説

`SetAt`配列が大きくなるわけではありません。 配列`SetAtGrow`を自動的に拡張する場合に使用します。

インデックス値が配列内の有効な位置を表していることを確認する必要があります。 範囲外の場合は、ライブラリのデバッグ バージョンがアサートします。

次の表に、 に似たその他`CObArray::SetAt`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**無効なセットアット( INT_PTR** `nIndex` **, バイト**`newElement`**);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**ボイドセットアット(INT_PTR、DWORD);** `nIndex` **, DWORD** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**無効セットアット(INT_PTR、**`nIndex`**ボイド**<strong>\*</strong>`newElement`**);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**ボイドセットアット(INT_PTR** `nIndex` **、LPCTSTR);** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**ボイドセットアット(INT_PTR** `nIndex` **、UINT);** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ボイドセットアット(INT_PTR、WORD);** `nIndex` **, WORD** `newElement` **);**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>コブアレイ::セットアックグロー

指定したインデックス位置に配列要素を設定します。

```
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上の整数インデックス。

*新しい要素*<br/>
この配列に追加するオブジェクト ポインター。 NULL 値を使用できます。

### <a name="remarks"></a>解説

必要に応じて配列が自動的に拡張されます (つまり、新しい要素に対応するように上限が調整されます)。

次の表に、 に似たその他`CObArray::SetAtGrow`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**無効なセットアズグロー( INT_PTR** `nIndex` **, バイト**`newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**ボイドセットアズグロー(INT_PTR、DWORD);** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**ボイドセットアズグロー(INT_PTR、**`nIndex`**ボイド**<strong>\*</strong>`newElement`**);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**ボイドセットアットグロー(INT_PTR** `nIndex` **、LPCTSTR);** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**ボイドセタットグロー(INT_PTR** `nIndex` **、UINT);** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**ボイドセットアズグロー(INT_PTR、WORD);** `nIndex` **, WORD** `newElement` **);**<br /><br /> **スロー( C\*メモリ例外 );**|

### <a name="example"></a>例

  すべてのコレクションの例で使用されるクラスの一覧については[、CObList::CObList](../../mfc/reference/coblist-class.md#coblist)を`CAge`参照してください。

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

このプログラムの結果は次のとおりです。

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>::セットサイズ

空または既存の配列のサイズを設定します。必要に応じてメモリを割り当てます。

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>パラメーター

*nNewサイズ*<br/>
新しい配列サイズ (要素数)。 0 以上である必要があります。

*nグローバイ*<br/>
サイズの増加が必要な場合に割り当てる要素スロットの最小数。

### <a name="remarks"></a>解説

新しいサイズが古いサイズより小さい場合、配列は切り捨てられ、未使用のメモリはすべて解放されます。 効率を高めるために、`SetSize`配列を使用する前に配列のサイズを設定する呼び出し。 これにより、項目が追加されるたびに配列を再割り当てしてコピーする必要がなくなります。

*nGrowBy*パラメーターは、配列が拡張している間、内部メモリ割り当てに影響します。 この値の使用は、 と で`GetSize`報告`GetUpperBound`される配列サイズには影響しません。

配列のサイズが大きくなると、新しく割り当てられた**すべての CObject**<strong>\*</strong>ポインターは NULL に設定されます。

次の表に、 に似たその他`CObArray::SetSize`のメンバー関数を示します。

|クラス|メンバー関数|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**無効な SetSize ( INT_PTR** `nNewSize` **、 int** `nGrowBy` **= -1 );**<br /><br /> **スロー( C\*メモリ例外 );**|

### <a name="example"></a>例

  [の](#getdata)例を参照してください。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CStringArray クラス](../../mfc/reference/cstringarray-class.md)<br/>
[CPtrArray クラス](../../mfc/reference/cptrarray-class.md)<br/>
[CByteArray クラス](../../mfc/reference/cbytearray-class.md)<br/>
[クラス](../../mfc/reference/cwordarray-class.md)<br/>
[CDWordArray クラス](../../mfc/reference/cdwordarray-class.md)
