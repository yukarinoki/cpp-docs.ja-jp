---
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
ms.openlocfilehash: a996bca471ce82a7c2adaaad67670ddef417eda1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373280"
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
型指定されたポインター配列クラスの基本クラス。配列クラス (`CObArray`または`CPtrArray`) でなければなりません。

*種類*<br/>
基本クラスの配列に格納されている要素の型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次のメソッドを使用します。](#add)|配列の末尾に新しい要素を追加します。 必要に応じて配列を拡張します。|
|[次のメソッドを追加します。](#append)|配列の内容を別の配列の末尾に追加します。 必要に応じて配列を拡張します。|
|[コピーの配列::コピー](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|
|[要素の配列::要素](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|
|[クタイププターアレイ::ゲットアット](#getat)|指定されたインデックス位置にある値を返します。|
|[メソッドの配列::挿入](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|
|[クタイププター配列::セットアット](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|
|[クタイプ化された関数配列::セットアットグロー](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[メソッドの配列::演算子\[\]](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|

## <a name="remarks"></a>解説

または`CObArray`ではなく`CTypedPtrArray``CPtrArray`を使用する場合、C++ 型検査機能は、ポインター型の不一致によって発生するエラーを除去するのに役立ちます。

さらに、ラッパーは`CTypedPtrArray`、使用する場合に必要となるキャスティングの多くを実行`CObArray`します。 `CPtrArray`

すべての`CTypedPtrArray`関数がインラインであるため、このテンプレートを使用しても、コードのサイズや速度に大きな影響はありません。

の使用方法`CTypedPtrArray`の詳細については、「 コレクションと[テンプレート ベースのクラス](../../mfc/template-based-classes.md)」を参照してください。 [Collections](../../mfc/collections.md)

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a>次のメソッドを使用します。

このメンバー関数は`BASE_CLASS`**、::Add**を呼び出します。

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
配列に追加する要素の型を指定するテンプレート パラメーター。

*新しい要素*<br/>
この配列に追加する要素。

### <a name="return-value"></a>戻り値

追加された要素のインデックス。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::Add](../../mfc/reference/cobarray-class.md#add)」を参照してください。

## <a name="ctypedptrarrayappend"></a><a name="append"></a>次のメソッドを追加します。

このメンバー関数は`BASE_CLASS`、呼び出します ::Append**。

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラス。配列クラス ( [CObArray または CPtrArray](../../mfc/reference/cobarray-class.md) ) を指定する必要があります。 [CPtrArray](../../mfc/reference/cptrarray-class.md)

*種類*<br/>
基本クラスの配列に格納されている要素の型。

*src*<br/>
配列に追加する要素のソース。

### <a name="return-value"></a>戻り値

追加された最初の要素のインデックス。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::Append](../../mfc/reference/cobarray-class.md#append)」を参照してください。

## <a name="ctypedptrarraycopy"></a><a name="copy"></a>コピーの配列::コピー

このメンバー関数は`BASE_CLASS`**、::Copy**を呼び出します。

```
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラス。配列クラス ( [CObArray または CPtrArray](../../mfc/reference/cobarray-class.md) ) を指定する必要があります。 [CPtrArray](../../mfc/reference/cptrarray-class.md)

*種類*<br/>
基本クラスの配列に格納されている要素の型。

*src*<br/>
配列にコピーする要素のソース。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)」を参照してください。

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a>要素の配列::要素

このインライン関数は`BASE_CLASS`**、::ElementAt**を呼び出します。

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
この配列に格納されている要素の型を指定するテンプレート パラメーター。

*nIndex*<br/>
0 以上、および`BASE_CLASS`**::GetUpperBound**によって返される値以下の整数インデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定された位置にある要素への一時的な参照。 この要素は、テンプレート パラメータ*TYPE*で指定された型です。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)」を参照してください。

## <a name="ctypedptrarraygetat"></a><a name="getat"></a>クタイププターアレイ::ゲットアット

このインライン関数は`BASE_CLASS`**、::GetAt**を呼び出します。

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
配列に格納されている要素の型を指定するテンプレート パラメーター。

*nIndex*<br/>
0 以上、および`BASE_CLASS`**::GetUpperBound**によって返される値以下の整数インデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定された位置にある要素のコピー。 この要素は、テンプレート パラメータ*TYPE*で指定された型です。

### <a name="remarks"></a>解説

詳細な説明については、[次を](../../mfc/reference/cobarray-class.md#getat)参照してください。

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a>メソッドの配列::挿入

このメンバー関数は`BASE_CLASS`**、::InsertAt**を呼び出します。

```
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
[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)によって返される値よりも大きい可能性のある整数インデックス。

*種類*<br/>
基本クラスの配列に格納されている要素の型。

*新しい要素*<br/>
この配列に配置されるオブジェクト ポインター。 値**NULL**の*新しい要素*が許可されます。

*nカウント*<br/>
この要素を挿入する回数 (既定値は 1)。

*インデックスを作成します。*<br/>
によって返される値より大きい場合がある整数インデックス`CObArray::GetUpperBound`。

*BASE_CLASS*<br/>
型指定されたポインター配列クラスの基本クラス。配列クラス ( [CObArray または CPtrArray](../../mfc/reference/cobarray-class.md) ) を指定する必要があります。 [CPtrArray](../../mfc/reference/cptrarray-class.md)

*をクリックします。*<br/>
この配列に追加する要素を含む別の配列。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)」を参照してください。

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a>次のメソッドを実行します。

これらのインライン演算子は`BASE_CLASS`**::演算子 [ ] を**呼び出します。

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
配列に格納されている要素の型を指定するテンプレート パラメーター。

*nIndex*<br/>
0 以上、および`BASE_CLASS`**::GetUpperBound**によって返される値以下の整数インデックス。

### <a name="remarks"></a>解説

**const**でない配列に対して呼び出される最初の演算子は、代入ステートメントの右 (r 値) または左 (左辺値) で使用できます。 **2**番目の定数配列に対して呼び出される、右側でのみ使用できます。

ライブラリのデバッグ バージョンは、下付き文字 (代入ステートメントの左側または右側) が範囲外にある場合にアサートします。

## <a name="ctypedptrarraysetat"></a><a name="setat"></a>クタイププター配列::セットアット

このメンバー関数は`BASE_CLASS`**、::SetAt**を呼び出します。

```
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上で[、CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)によって返される値以下の整数インデックス。

*種類*<br/>
基本クラスの配列に格納されている要素の型。

*Ptr*<br/>
nIndex の配列に挿入される要素へのポインター。 NULL 値を使用できます。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::SetAt」](../../mfc/reference/cobarray-class.md#setat)を参照してください。

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>クタイプ化された関数配列::セットアットグロー

このメンバー関数は`BASE_CLASS`**、::SetAtGrow**を呼び出します。

```
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
0 以上の整数インデックス。

*種類*<br/>
基本クラスの配列に格納されている要素の型。

*新しい要素*<br/>
この配列に追加するオブジェクト ポインター。 **NULL**値を使用できます。

### <a name="remarks"></a>解説

詳細な説明については[、「CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray クラス](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray クラス](../../mfc/reference/cobarray-class.md)
