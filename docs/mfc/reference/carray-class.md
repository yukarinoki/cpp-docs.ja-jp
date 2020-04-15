---
title: Cアレイクラス
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: 2c520a732edf54ebb36c07728ceb19791b351143
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377026"
---
# <a name="carray-class"></a>Cアレイクラス

C 配列と同様の配列をサポートしますが、必要に応じて動的に縮小および拡張できます。

## <a name="syntax"></a>構文

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>パラメーター

*種類*<br/>
配列に格納されているオブジェクトの型を指定するテンプレート パラメーター。 *TYPE*は、 によって`CArray`返されるパラメーターです。

*ARG_TYPE*<br/>
配列に格納されているオブジェクトにアクセスするために使用される引数の型を指定するテンプレート パラメーター。 多くの場合 *、TYPE*への参照です。 *ARG_TYPE*は に渡されるパラメータです`CArray`。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cアレイ::Cアレイ](#carray)|空の配列を生成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CArray::追加](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|
|[CArray::追加](#append)|配列に別の配列を追加します。必要に応じて配列を拡張|
|[Cアレイ::コピー](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[CArray::エレメントアット](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[コレイ::フリーエクストラ](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|
|[コレイ::ゲットアット](#getat)|指定されたインデックス位置にある値を返します。|
|[を指定します。](#getcount)|この配列内の要素の数を取得します。|
|[を取得します。](#getdata)|配列内の要素へのアクセスを許可します。 NULL にすることができます。|
|[次の値を指定します。](#getsize)|この配列内の要素の数を取得します。|
|[コレー::ゲットアッパーバウンド](#getupperbound)|有効な最大のインデックスを返します。|
|[CArray::挿入](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[CArray::空](#isempty)|配列が空かどうかを判断します。|
|[すべてのコントロールを削除します。](#removeall)|この配列からすべての要素を削除します。|
|[コレイ::削除アット](#removeat)|特定のインデックス位置にある要素を削除します。|
|[コレイ::セットアット](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[コレイ::セットアックグロー](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|
|[配列::セットサイズ](#setsize)|この配列に含まれる要素の数を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator&#91;&#93;](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

配列インデックスは常に位置 0 から始まります。 現在の境界を超えて要素を追加するときに、上限を固定するか、配列を展開するかを決定できます。 一部の要素が null であっても、メモリは上限に連続して割り当てられます。

> [!NOTE]
> オブジェクトのサイズを変更`CArray`したり、オブジェクトに要素を追加したりするほとんどのメソッドでは[、memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)を使用して要素を移動します。 これは、コンストラクターの呼`memcpy_s`び出しを必要とするオブジェクトと互換性がないため、問題になります。 の項目`CArray`に 互換性`memcpy_s`がない場合は、適切なサイズの新しい`CArray`を作成する必要があります。 次に[、CArray::Copy](#copy)と[CArray:SetAt](#setat)を使用して新しい配列を設定する必要があります`memcpy_s`。

C 配列と同様に、`CArray`インデックス付き要素のアクセス時間は一定であり、配列のサイズとは無関係です。

> [!TIP]
> 配列を使用する前に[、SetSize](#setsize)を使用してサイズを設定し、配列にメモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

配列内の個々の要素のダンプが必要な場合は[、CDumpContext](../../mfc/reference/cdumpcontext-class.md)オブジェクトの深さを 1 以上に設定する必要があります。

このクラスの特定のメンバー関数は、クラスのほとんどの使用に合わせてカスタマイズする必要があるグローバル`CArray`ヘルパ関数を呼び出します。 「MFC マクロとグローバル」セクション[の「コレクション クラス ヘルパー](../../mfc/reference/collection-class-helpers.md) 」を参照してください。

配列クラスの派生は、リストの派生と似ています。

の使用方法の詳細については、 の記事 「 コレクション 」を参照してください。 [Collections](../../mfc/collections.md) `CArray`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="carrayadd"></a><a name="add"></a>CArray::追加

配列の末尾に新しい要素を追加し、配列を 1 ずつ増やします。

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*ARG_TYPE*<br/>
この配列内の要素を参照する引数の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
この配列に追加する要素。

### <a name="return-value"></a>戻り値

追加された要素のインデックス。

### <a name="remarks"></a>解説

[SetSize](#setsize)が 1 より`nGrowBy`大きい値で使用されている場合は、余分なメモリが割り当てられる可能性があります。 ただし、上限は 1 だけ増加します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

## <a name="carrayappend"></a><a name="append"></a>CArray::追加

ある配列の内容を別の配列の末尾に追加します。

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
配列に追加する要素のソース。

### <a name="return-value"></a>戻り値

追加された最初の要素のインデックス。

### <a name="remarks"></a>解説

配列は同じ型である必要があります。

必要に応`Append`じて、配列に追加された要素を格納するために余分なメモリを割り当てることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

## <a name="carraycarray"></a><a name="carray"></a>Cアレイ::Cアレイ

空の配列を生成します。

```
CArray();
```

### <a name="remarks"></a>解説

配列は一度に 1 つの要素を増やします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

## <a name="carraycopy"></a><a name="copy"></a>Cアレイ::コピー

このメンバー関数を使用して、配列の要素を別の配列にコピーします。

```
void Copy(const CArray& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
配列にコピーする要素のソース。

### <a name="remarks"></a>解説

ある配列の要素を別の配列の要素で上書きします。

`Copy`メモリを解放しません。ただし、必要に応`Copy`じて、配列にコピーされた要素を格納するために余分なメモリを割り当てる場合があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

## <a name="carrayelementat"></a><a name="elementat"></a>CArray::エレメントアット

配列内の指定した要素への一時的な参照を返します。

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上で[、GetUpperBound](#getupperbound)によって返される値以下の整数インデックス。

### <a name="return-value"></a>戻り値

配列要素への参照。

### <a name="remarks"></a>解説

配列の左辺代入演算子を実装するために使用されます。

### <a name="example"></a>例

  [GetSize](#getsize)の例を参照してください。

## <a name="carrayfreeextra"></a><a name="freeextra"></a>コレイ::フリーエクストラ

配列の拡大中に割り当てられた余分なメモリを解放します。

```
void FreeExtra();
```

### <a name="remarks"></a>解説

この関数は、配列のサイズや上限には影響しません。

### <a name="example"></a>例

  [GetData](#getdata)の例を参照してください。

## <a name="carraygetat"></a><a name="getat"></a>コレイ::ゲットアット

指定したインデックス位置にある配列要素を返します。

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
配列要素の型を指定するテンプレート パラメーター。

*nIndex*<br/>
0 以上で[、GetUpperBound](#getupperbound)によって返される値以下の整数インデックス。

### <a name="return-value"></a>戻り値

現在このインデックスにある配列要素。

### <a name="remarks"></a>解説

負の値または返された値より大きい値を渡`GetUpperBound`すと、アサーションが失敗します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

## <a name="carraygetcount"></a><a name="getcount"></a>を指定します。

配列要素の数を返します。

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>戻り値

配列内の項目の数。

### <a name="remarks"></a>解説

配列内の要素の数を取得します。 インデックスは 0 から始まるので、サイズは最大のインデックスより 1 大きくなります。 このメソッドを呼び出すと[、CArray::GetSize](#getsize)メソッドと同じ結果が生成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

## <a name="carraygetdata"></a><a name="getdata"></a>を取得します。

このメンバー関数を使用して、配列内の要素に直接アクセスできます。

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
配列要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

配列要素へのポインター。

### <a name="remarks"></a>解説

使用できる要素がない場合は`GetData`、null 値を返します。

配列の要素に直接アクセスすると作業の速度が向上しますが、呼び出す際`GetData`は注意が必要です。エラーが発生すると、配列の要素に直接影響します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

## <a name="carraygetsize"></a><a name="getsize"></a>次の値を指定します。

配列のサイズを返します。

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>解説

インデックスは 0 から始まるので、サイズは最大のインデックスより 1 大きくなります。 このメソッドを呼び出すと[、CArray::GetCount](#getcount)メソッドと同じ結果が生成されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

## <a name="carraygetupperbound"></a><a name="getupperbound"></a>コレー::ゲットアッパーバウンド

この配列の現在の上限を返します。

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>解説

配列インデックスは 0 から始まるので、この関数は 1`GetSize`より小さい値を返します。

条件`GetUpperBound( )`= -1 は、配列に要素が含まれていることを示します。

### <a name="example"></a>例

  [CArray::GetAt](#getat)の例を参照してください。

## <a name="carrayinsertat"></a><a name="insertat"></a>CArray::挿入

の最初のバージョン`InsertAt`では、配列内の指定したインデックスに 1 つの要素 (または要素の複数のコピー) が挿入されます。

```
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
によって返される値より大きい場合がある整数インデックス`GetUpperBound`。

*ARG_TYPE*<br/>
この配列内の要素の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
この配列に配置する要素。

*nカウント*<br/>
この要素を挿入する回数 (既定値は 1)。

*インデックスを作成します。*<br/>
[GetUpperBound](#getupperbound)によって返される値より大きい整数インデックス。

*をクリックします。*<br/>
この配列に追加する要素を含む別の配列。

### <a name="remarks"></a>解説

このプロセスでは、このインデックスの既存の要素を (インデックスをインクリメントして) 上に移動し、その上にあるすべての要素を上に移動します。

2 番目のバージョンでは`CArray`*、nStartIndex*の位置から、別のコレクションからすべての要素を挿入します。

これに`SetAt`対し、この関数は指定された配列要素を置き換え、要素をシフトしません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

## <a name="carrayisempty"></a><a name="isempty"></a>CArray::空

配列が空かどうかを判断します。

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

配列に要素が含まれなかった場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="carrayoperator-"></a><a name="operator_at"></a>CArray::演算子\[\]

これらの添字演算子は[、SetAt](#setat)関数と[GetAt](#getat)関数の代わりに便利です。

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
この配列内の要素の型を指定するテンプレート パラメーター。

*nIndex*<br/>
アクセスする要素のインデックス。

### <a name="remarks"></a>解説

**const**でない配列に対して呼び出される最初の演算子は、代入ステートメントの右 (r 値) または左 (左辺値) で使用できます。 **2**番目の定数配列は、右側でのみ使用できます。

ライブラリのデバッグ バージョンは、下付き文字 (代入ステートメントの左側または右側) が範囲外にある場合にアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

## <a name="carrayrelocateelements"></a><a name="relocateelements"></a>コレー::再配置要素

配列が拡張または縮小する必要があるときに、データを新しいバッファーに再配置します。

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
要素の配列の新しいバッファー。

*Pdata*<br/>
要素の古い配列。

*nカウント*<br/>
古い配列の要素の数。

### <a name="remarks"></a>解説

*pNewData*は常にすべての*pData*要素を保持するのに十分な大きさです。

[CArray](../../mfc/reference/carray-class.md)実装では、配列が拡張または縮小する必要がある場合[(SetSize](#setsize)または[FreeExtra](#freeextra)が呼び出されたときに) 古いデータを新しいバッファーにコピーするには、このメソッドを使用します。 既定の実装では、データがコピーされます。

要素に自身のメンバーへのポインターが含まれている配列、または別の構造体に配列要素の 1 つへのポインターが含まれている配列の場合、ポインターはプレーン コピーでは更新されません。 この場合、関連する型の特殊化`RelocateElements`を実装することで、ポインターを修正できます。 また、データのコピーも担当します。

## <a name="carrayremoveall"></a><a name="removeall"></a>すべてのコントロールを削除します。

この配列からすべての要素を削除します。

```
void RemoveAll();
```

### <a name="remarks"></a>解説

配列が既に空の場合でも、関数は動作します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

## <a name="carrayremoveat"></a><a name="removeat"></a>コレイ::削除アット

配列内の指定したインデックス位置から開始する 1 つ以上の要素を削除します。

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上で[、GetUpperBound](#getupperbound)によって返される値以下の整数インデックス。

*nカウント*<br/>
削除する要素の数を指定します。

### <a name="remarks"></a>解説

プロセスでは、削除された要素の上にあるすべての要素をシフトダウンします。 配列の上限を減らしますが、メモリは解放されません。

削除ポイントの上の配列に含まれている要素よりも多くの要素を削除しようとすると、ライブラリのデバッグ バージョンがアサートされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

## <a name="carraysetat"></a><a name="setat"></a>コレイ::セットアット

指定したインデックス位置に配列要素を設定します。

```
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上で[、GetUpperBound](#getupperbound)によって返される値以下の整数インデックス。

*ARG_TYPE*<br/>
配列要素の参照に使用する引数の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
指定した位置に格納される新しい要素の値。

### <a name="remarks"></a>解説

`SetAt`配列が大きくなるわけではありません。 配列を自動的に拡張する場合は[、SetAtGrow](#setatgrow)を使用します。

インデックス値が配列内の有効な位置を表していることを確認する必要があります。 範囲外の場合は、ライブラリのデバッグ バージョンがアサートします。

### <a name="example"></a>例

  [GetAt](#getat)の例を参照してください。

## <a name="carraysetatgrow"></a><a name="setatgrow"></a>コレイ::セットアックグロー

指定したインデックス位置に配列要素を設定します。

```
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上の整数インデックス。

*ARG_TYPE*<br/>
配列内の要素の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
この配列に追加する要素。 NULL 値を使用できます。

### <a name="remarks"></a>解説

必要に応じて配列が自動的に拡張されます (つまり、新しい要素に対応するように上限が調整されます)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

## <a name="carraysetsize"></a><a name="setsize"></a>配列::セットサイズ

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

新しいサイズが古いサイズより小さい場合、配列は切り捨てられ、未使用のメモリはすべて解放されます。

この関数を使用して、配列の使用を開始する前に配列のサイズを設定します。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。

*nGrowBy*パラメーターは、配列が拡張している間、内部メモリ割り当てに影響します。 この関数の使用は[、GetSize](#getsize)および[GetUpperBound](#getupperbound)で報告される配列サイズに影響を与えることはありません。 既定値を使用する場合、MFC は、メモリの断片化を回避し、ほとんどの場合の効率を最適化するために計算された方法でメモリを割り当てます。

### <a name="example"></a>例

  [GetData](#getdata)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CObArray クラス](../../mfc/reference/cobarray-class.md)<br/>
[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)
