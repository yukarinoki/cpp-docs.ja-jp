---
description: '詳細情報: CTypedPtrArray クラス'
title: CTypedPtrArray クラス
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
ms.openlocfilehash: 07d254072a51a56759a3dbe569c36ff65d199cfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345005"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray クラス

`CPtrArray` クラスまたは `CObArray`クラスのオブジェクトに対してタイプセーフな "ラッパー" を提供します。

## <a name="syntax"></a>構文

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラスです。は、配列クラス (または) である必要があり `CObArray` `CPtrArray` ます。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTypedPtrArray:: Add](#add)|配列の末尾に新しい要素を追加します。 必要に応じて配列を拡大します。|
|[CTypedPtrArray:: Append](#append)|ある配列の内容を別の配列の末尾に追加します。 必要に応じて配列を拡大します。|
|[CTypedPtrArray:: Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[CTypedPtrArray:: ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[CTypedPtrArray:: GetAt](#getat)|指定されたインデックス位置にある値を返します。|
|[CTypedPtrArray:: InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[CTypedPtrArray:: SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[CTypedPtrArray:: SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTypedPtrArray:: operator \[\]](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

またはではなくを使用すると `CTypedPtrArray` `CPtrArray` `CObArray` 、C++ の型チェック機能によって、ポインター型の不一致によって発生するエラーを解消できます。

また、ラッパーは `CTypedPtrArray` またはを使用した場合に必要となる多くのキャストを実行し `CObArray` `CPtrArray` ます。

すべての `CTypedPtrArray` 関数がインラインであるため、このテンプレートを使用してもコードのサイズや速度に大きな影響はありません。

の使用方法の詳細については `CTypedPtrArray` 、「アーティクル [コレクション](../../mfc/collections.md) と [テンプレートベースのクラス](../../mfc/template-based-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>要件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a> CTypedPtrArray:: Add

このメンバー関数 `BASE_CLASS` **は、:: Add** を呼び出します。

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
配列に追加する要素の型を指定するテンプレートパラメーター。

*(Newelement*<br/>
この配列に追加する要素。

### <a name="return-value"></a>戻り値

追加された要素のインデックス。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: Add](../../mfc/reference/cobarray-class.md#add)」を参照してください。

## <a name="ctypedptrarrayappend"></a><a name="append"></a> CTypedPtrArray:: Append

このメンバー関数 `BASE_CLASS` は、:: Append * * を呼び出します。

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラスです。は、配列クラス ( [CObArray](../../mfc/reference/cobarray-class.md) または [CPtrArray](../../mfc/reference/cptrarray-class.md)) である必要があります。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

*src*<br/>
配列に追加する要素のソース。

### <a name="return-value"></a>戻り値

追加された最初の要素のインデックス。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: Append](../../mfc/reference/cobarray-class.md#append)」を参照してください。

## <a name="ctypedptrarraycopy"></a><a name="copy"></a> CTypedPtrArray:: Copy

このメンバー関数 `BASE_CLASS` **は、:: Copy** を呼び出します。

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラスです。は、配列クラス ( [CObArray](../../mfc/reference/cobarray-class.md) または [CPtrArray](../../mfc/reference/cptrarray-class.md)) である必要があります。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

*src*<br/>
配列にコピーされる要素のソース。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: Copy](../../mfc/reference/cobarray-class.md#copy)」を参照してください。

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a> CTypedPtrArray:: ElementAt

このインライン関数 `BASE_CLASS` **は、:: elementat** を呼び出します。

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
この配列に格納されている要素の型を指定するテンプレートパラメーター。

*nIndex*<br/>
0以上で、 `BASE_CLASS` **:: system.array.getupperbound** によって返された値以下の整数のインデックス。

### <a name="return-value"></a>戻り値

*NIndex* によって指定された位置にある要素への一時的な参照。 この要素は、テンプレートパラメーター *型* によって指定された型です。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)」を参照してください。

## <a name="ctypedptrarraygetat"></a><a name="getat"></a> CTypedPtrArray:: GetAt

このインライン関数 `BASE_CLASS` **は、:: GetAt** を呼び出します。

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
配列に格納されている要素の型を指定するテンプレートパラメーター。

*nIndex*<br/>
0以上で、 `BASE_CLASS` **:: system.array.getupperbound** によって返された値以下の整数のインデックス。

### <a name="return-value"></a>戻り値

*NIndex* によって指定された位置にある要素のコピー。 この要素は、テンプレートパラメーター *型* によって指定された型です。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: GetAt](../../mfc/reference/cobarray-class.md#getat) 」を参照してください。

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a> CTypedPtrArray:: InsertAt

このメンバー関数 `BASE_CLASS` **は、:: InsertAt** を呼び出します。

```cpp
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[CObArray:: system.array.getupperbound](../../mfc/reference/cobarray-class.md#getupperbound)によって返された値よりも大きい可能性のある整数インデックス。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

*(Newelement*<br/>
この配列に配置されるオブジェクトポインター。 値が **NULL** の *newelement* は使用できます。

*nCount*<br/>
この要素を挿入する回数 (既定値は 1)。

*nStartIndex*<br/>
によって返される値よりも大きい可能性のある整数インデックス `CObArray::GetUpperBound` 。

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラスです。は、配列クラス ( [CObArray](../../mfc/reference/cobarray-class.md) または [CPtrArray](../../mfc/reference/cptrarray-class.md)) である必要があります。

*pNewArray*<br/>
この配列に追加する要素を格納している別の配列。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: InsertAt](../../mfc/reference/cobarray-class.md#insertat)」を参照してください。

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a> CTypedPtrArray:: operator []

これらのインライン演算子 `BASE_CLASS` **は、:: operator []** を呼び出します。

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
配列に格納されている要素の型を指定するテンプレートパラメーター。

*nIndex*<br/>
0以上で、 `BASE_CLASS` **:: system.array.getupperbound** によって返された値以下の整数のインデックス。

### <a name="remarks"></a>解説

ではない配列に対して呼び出される最初の演算子は、 **`const`** 代入ステートメントの right (右辺値) または left (左辺値) のいずれかで使用できます。 配列に対して呼び出される2番目のは、 **`const`** 右側でのみ使用できます。

ライブラリのデバッグバージョンは、添字 (代入ステートメントの左側または右側) が範囲外である場合にアサートします。

## <a name="ctypedptrarraysetat"></a><a name="setat"></a> CTypedPtrArray:: SetAt

このメンバー関数 `BASE_CLASS` **は、:: SetAt** を呼び出します。

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[CObArray:: system.array.getupperbound](../../mfc/reference/cobarray-class.md#getupperbound)によって返された値以下の、0以上の整数のインデックス。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

*ptr*<br/>
NIndex で配列に挿入される要素へのポインター。 NULL 値が許可されます。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: SetAt](../../mfc/reference/cobarray-class.md#setat)」を参照してください。

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a> CTypedPtrArray:: SetAtGrow

このメンバー関数 `BASE_CLASS` **は、:: SetAtGrow** を呼び出します。

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0以上の整数のインデックスです。

*TYPE*<br/>
基本クラス配列に格納されている要素の型。

*(Newelement*<br/>
この配列に追加するオブジェクトポインター。 **NULL** 値が許可されます。

### <a name="remarks"></a>解説

詳細については、「 [CObArray:: SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray クラス](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray クラス](../../mfc/reference/cobarray-class.md)
