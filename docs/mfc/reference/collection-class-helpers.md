---
description: '詳細情報: コレクションクラスヘルパー'
title: コレクション クラスのヘルパー
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 9d3838ba0ba05441debb183e47d7df4e39229742
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331387"
---
# <a name="collection-class-helpers"></a>コレクション クラスのヘルパー

コレクションクラス、 `CMap` `CList` 、およびは、 `CArray` 要素の比較、コピー、およびシリアル化などの目的で、テンプレート化されたグローバルヘルパー関数を使用します。 、、およびに基づくクラスの実装の一部として `CMap` `CList` `CArray` 、マップ、リスト、または配列に格納されているデータ型に合わせて調整されたバージョンで、必要に応じてこれらの関数をオーバーライドする必要があります。 などのヘルパー関数をオーバーライドする方法の詳細については、 `SerializeElements` 「 [コレクションの作成方法](../../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。 Type-Safe コレクションの作成方法に関する記事をご覧ください。 `ConstructElements`と `DestructElements` は非推奨とされていることに注意してください。

Microsoft Foundation Class ライブラリには、コレクションクラスをカスタマイズするのに役立つ、afxtempl.h の次のグローバル関数が用意されています。

### <a name="collection-class-helpers"></a>コレクション クラスのヘルパー

|名前|説明|
|-|-|
|[CompareElements](#compareelements)|要素が同じであるかどうかを示します。|
|[CopyElements](#copyelements)|ある配列から別の配列に要素をコピーします。|
|[DumpElements](#dumpelements)|ストリーム指向の診断出力を提供します。|
|[HashKey](#hashkey)|ハッシュキーを計算します。|
|[SerializeElements](#serializeelements)|アーカイブとの間で要素を格納または取得します。|

## <a name="compareelements"></a><a name="compareelements"></a> CompareElements

[Cmap__lookup](cmap-class.md#lookup)と[cmap__operator &#91;&#93;](cmap-class.md#operator_at)によって間接的に、[clist:: Find] (clist-class not_found md # clist__find と間接的に呼び出されます。

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
比較する最初の要素の型。

*pElement1*<br/>
比較する最初の要素へのポインター。

*ARG_TYPE*<br/>
比較する2番目の要素の型。

*pElement2*<br/>
比較する2番目の要素へのポインター。

### <a name="return-value"></a>戻り値

*PElement1* が指すオブジェクトが *pElement2* が指すオブジェクトと等しい場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

の呼び出しでは、 `CMap` `CMap` テンプレートパラメーター *KEY* と *ARG_KEY* が使用されます。

既定の実装では、 *\* pElement1* と *\* pElement2* の比較結果が返されます。 アプリケーションに適した方法で要素を比較するように、この関数をオーバーライドします。

C++ 言語では、 `==` 単純型 (、、など) の比較演算子 () が定義されてい **`char`** **`int`** **`float`** ますが、クラスと構造体の比較演算子は定義されていません。 またはを使用し `CompareElements` て、それを使用するコレクションクラスの1つをインスタンス化する場合は、 `CompareElements` 適切な値を返すバージョンで比較演算子またはオーバーロードを定義する必要があります。

### <a name="requirements"></a>要件

   **ヘッダー:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a> CopyElements

この関数は、 [CArray:: Append](carray-class.md#append) と [CArray:: Copy](carray-class.md#copy)によって直接呼び出されます。

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
コピーする要素の型を指定するテンプレートパラメーター。

*pDest*<br/>
要素がコピーされる先へのポインター。

*.Psrc*<br/>
コピーされる要素のソースへのポインター。

*nCount*<br/>
コピーされる要素の数。

### <a name="remarks"></a>解説

既定の実装では、単純な代入演算子 () を使用して **=** コピー操作を実行します。 コピーされる型にオーバーロードされた operator = がない場合、既定の実装はビットごとのコピーを実行します。

この機能およびその他のヘルパー関数の実装の詳細については、「 [コレクションの作成方法: Type-Safe コレクションの作成方法](../how-to-make-a-type-safe-collection.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxtempl.h

## <a name="dumpelements"></a><a name="dumpelements"></a> DumpElements

オーバーライドされた場合に、コレクションの要素のテキスト形式でストリーム指向の診断出力を提供します。

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
要素をダンプするためのコンテキストをダンプします。

*TYPE*<br/>
要素の型を指定するテンプレートパラメーター。

*pElements*<br/>
ダンプされる要素へのポインター。

*nCount*<br/>
ダンプされる要素の数。

### <a name="remarks"></a>解説

`CArray::Dump`、、およびの各関数は、 `CList::Dump` `CMap::Dump` ダンプの深さが0より大きい場合にこのを呼び出します。

既定の実装では、何も行われません。 コレクションの要素がから派生している場合 `CObject` 、通常、オーバーライドはコレクションの要素を反復処理し、 `Dump` 各要素に対してを呼び出します。

### <a name="requirements"></a>要件

  **ヘッダー** afxtempl.h

## <a name="hashkey"></a><a name="hashkey"></a> HashKey

指定されたキーのハッシュ値を計算します。

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>パラメーター

*ARG_KEY*<br/>
マップキーへのアクセスに使用するデータ型を指定するテンプレートパラメーター。

*key*<br/>
ハッシュ値を計算するキー。

### <a name="return-value"></a>戻り値

キーのハッシュ値。

### <a name="remarks"></a>解説

この関数は、Cmap: [: RemoveKey](cmap-class.md#removekey) によって直接呼び出され、 [Cmap:: Lookup](cmap-class.md#lookup) および [cmap:: Operator &#91;&#93;](cmap-class.md#operator_at)によって間接的に呼び出されます。

既定の実装では、 *キー* を4つの位置で右にシフトしてハッシュ値を作成します。 アプリケーションに適したハッシュ値を返すように、この関数をオーバーライドします。

### <a name="example"></a>例

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>要件

  **ヘッダー** afxtempl.h

## <a name="serializeelements"></a><a name="serializeelements"></a> SerializeElements

[CArray](carray-class.md)、 [CList](clist-class.md)、および [CMap](cmap-class.md) は、この関数を呼び出して要素をシリアル化します。

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
要素の型を指定するテンプレートパラメーター。

*ar*<br/>
アーカイブするアーカイブオブジェクト。

*pElements*<br/>
アーカイブされる要素へのポインター。

*nCount*<br/>
アーカイブされている要素の数

### <a name="remarks"></a>解説

既定の実装では、ビットごとの読み取りまたは書き込みが行われます。

この機能およびその他のヘルパー関数の実装の詳細については、「 [コレクションの作成方法: Type-Safe コレクションの作成方法](../how-to-make-a-type-safe-collection.md)」を参照してください。

### <a name="example"></a>例

「 [コレクションの作成方法](../how-to-make-a-type-safe-collection.md)」の記事の例を参照してください。 Type-Safe コレクションです。

### <a name="requirements"></a>要件

  **ヘッダー** afxtempl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CMap クラス](cmap-class.md)<br/>
[CList クラス](clist-class.md)<br/>
[CArray クラス](carray-class.md)
