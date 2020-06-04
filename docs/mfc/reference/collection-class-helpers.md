---
title: コレクション クラスのヘルパー
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 05fe49a4d8e6de92c584d40f3871f3efb906c7c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374810"
---
# <a name="collection-class-helpers"></a>コレクション クラスのヘルパー

コレクション クラス`CMap` `CList`、、`CArray`およびテンプレート化されたグローバル ヘルパ関数を使用して、要素の比較、コピー、シリアル化などを行います。 に基づく`CMap``CList``CArray`クラスの実装の一部として、マップ、リスト、または配列に格納されているデータの種類に合わせて調整されたバージョンを使用して、これらの関数を必要に応じてオーバーライドする必要があります。 などの`SerializeElements`ヘルパー関数のオーバーライドの詳細については、「[コレクション : タイプ セーフコレクションを作成する方法](../../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。 また`ConstructElements`、`DestructElements`非推奨であることに注意してください。

Microsoft Foundation クラス ライブラリは、コレクション クラスをカスタマイズするために afxtempl.h で次のグローバル関数を提供します。

### <a name="collection-class-helpers"></a>コレクション クラスのヘルパー

|||
|-|-|
|[CompareElements](#compareelements)|要素が同じかどうかを示します。|
|[CopyElements](#copyelements)|配列間で要素をコピーします。|
|[DumpElements](#dumpelements)|ストリーム指向の診断出力を提供します。|
|[ハッシュキー](#hashkey)|ハッシュ キーを計算します。|
|[SerializeElements](#serializeelements)|アーカイブに対する要素の格納または取得を行います。|

## <a name="compareelements"></a><a name="compareelements"></a>要素を比較する

[CList::Find](clist-class.md#not_found.md#clist__findによって直接呼び出され[、 &#91;&#93;cmap__lookup](cmap-class.md#lookup)と[cmap__operator](cmap-class.md#operator_at)によって間接的に呼び出されます。

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
比較する最初の要素の型。

*1*<br/>
比較する最初の要素へのポインター。

*ARG_TYPE*<br/>
比較する 2 番目の要素の型。

*2*<br/>
比較する 2 番目の要素へのポインター。

### <a name="return-value"></a>戻り値

*pElement1*が指すオブジェクトが*pElement2*によって指されるオブジェクトと等しい場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

呼`CMap`び出し`CMap`では、テンプレート パラメータ*KEY*と*ARG_KEY*を使用します。

既定の実装では*\*、pElement1*と*\*pElement2*の比較の結果が返されます。 アプリケーションに適した方法で要素を比較するように、この関数をオーバーライドします。

C++ 言語は単純型 ( `==`**char**、 **int**、 **float**など ) の比較演算子 ( ) を定義しますが、クラスと構造体の比較演算子は定義しません。 またはそれを使用`CompareElements`するコレクション クラスのいずれかをインスタンス化する場合は、比較演算子を定義するか、適切な値を返す`CompareElements`バージョンをオーバーロードする必要があります。

### <a name="requirements"></a>必要条件

   **ヘッダー:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a>要素のコピー

この関数は[、CArray::追加](carray-class.md#append)と[CArray::コピー](carray-class.md#copy)によって直接呼び出されます。

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
コピーする要素の型を指定するテンプレート パラメーター。

*pDest*<br/>
要素がコピーされるコピー先へのポインター。

*pSrc*<br/>
コピーする要素のソースへのポインター。

*nカウント*<br/>
コピーする要素の数。

### <a name="remarks"></a>解説

既定の実装では、単純な代入演算子**=**( ) を使用してコピー操作を実行します。 コピーされる型にオーバーロードされた operator= がない場合、既定の実装ではビットごとのコピーが実行されます。

この関数およびその他のヘルパー関数の実装については、「コレクション[: タイプ セーフコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxtempl.h

## <a name="dumpelements"></a><a name="dumpelements"></a>ダンプ要素

オーバーライドされたときにコレクションの要素に対して、ストリーム指向の診断出力をテキスト形式で提供します。

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
要素をダンプするためのダンプ コンテキスト。

*種類*<br/>
要素の型を指定するテンプレート パラメーター。

*要素*<br/>
ダンプされる要素へのポインター。

*nカウント*<br/>
ダンプする要素の数。

### <a name="remarks"></a>解説

`CArray::Dump`、、`CList::Dump`および`CMap::Dump`関数は、ダンプの深さが 0 より大きい場合にこれを呼び出します。

既定の実装では、何も行われません。 コレクションの要素が から`CObject`派生している場合、オーバーライドは通常、コレクションの要素を反復処理して、各`Dump`要素を順番に呼び出します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxtempl.h

## <a name="hashkey"></a><a name="hashkey"></a>ハッシュキー

指定されたキーのハッシュ値を計算します。

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
マップ キーへのアクセスに使用するデータ型を指定するテンプレート パラメーター。

*key*<br/>
ハッシュ値を計算するキー。

### <a name="return-value"></a>戻り値

キーのハッシュ値。

### <a name="remarks"></a>解説

この関数は[、CMap::RemoveKey](cmap-class.md#removekey)によって直接呼び出され[、CMap::ルックアップ](cmap-class.md#lookup)と[CMap::演算子 &#91;&#93;](cmap-class.md#operator_at)によって間接的に呼び出されます。

既定の実装では、*キー*を 4 つ右にシフトすることでハッシュ値を作成します。 アプリケーションに適したハッシュ値を返す場合は、この関数をオーバーライドします。

### <a name="example"></a>例

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afxtempl.h

## <a name="serializeelements"></a><a name="serializeelements"></a>要素をシリアル化する

[CArray](carray-class.md) [、CList](clist-class.md)、および[CMap](cmap-class.md)は、この関数を呼び出して要素をシリアル化します。

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
要素の型を指定するテンプレート パラメーター。

*ar*<br/>
アーカイブの対象またはアーカイブに使用するアーカイブ オブジェクト。

*要素*<br/>
アーカイブされる要素へのポインター。

*nカウント*<br/>
アーカイブされる要素の数

### <a name="remarks"></a>解説

既定の実装では、ビットごとの読み取りまたは書き込みを行います。

この関数およびその他のヘルパー関数の実装については、「コレクション[: タイプ セーフコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)」を参照してください。

### <a name="example"></a>例

「[コレクション: タイプ セーフなコレクションを作成する方法」の例を](../how-to-make-a-type-safe-collection.md)参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxtempl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CMap クラス](cmap-class.md)<br/>
[CList クラス](clist-class.md)<br/>
[Cアレイクラス](carray-class.md)
