---
description: '詳細情報: CTypedPtrList クラス'
title: CTypedPtrList クラス
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 353e9af00b1366b260ce3cb3689018a8e4e370c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318534"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList クラス

`CPtrList`クラスのオブジェクトに対してタイプ セーフな "ラップ" が用意されています。

## <a name="syntax"></a>構文

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインターリストクラスの基本クラスです。はポインターリストクラス (または) である必要があり `CObList` `CPtrList` ます。

*TYPE*<br/>
基底クラスリストに格納されている要素の型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTypedPtrList:: AddHead](#addhead)|要素 (または別のリスト内のすべての要素) をリストの先頭に追加します (新しい head を作成します)。|
|[CTypedPtrList:: AddTail](#addtail)|要素 (または別のリスト内のすべての要素) をリストの末尾に追加します (新しい末尾を作成します)。|
|[CTypedPtrList:: GetAt](#getat)|指定した位置にある要素を取得します。|
|[CTypedPtrList:: GetHead](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[CTypedPtrList:: GetNext](#getnext)|反復処理の対象となる次の要素を取得します。|
|[CTypedPtrList:: GetPrev](#getprev)|反復処理する前の要素を取得します。|
|[CTypedPtrList:: GetTail](#gettail)|リストの末尾の要素を返します (空にすることはできません)。|
|[CTypedPtrList:: RemoveHead](#removehead)|リストの先頭から要素を削除します。|
|[CTypedPtrList:: RemoveTail](#removetail)|リストの末尾から要素を削除します。|
|[CTypedPtrList:: SetAt](#setat)|指定された位置に要素を設定します。|

## <a name="remarks"></a>解説

またはではなくを使用すると `CTypedPtrList` `CObList` `CPtrList` 、C++ の型チェック機能によって、ポインター型の不一致によって発生するエラーを解消できます。

また、ラッパーは `CTypedPtrList` またはを使用した場合に必要となる多くのキャストを実行し `CObList` `CPtrList` ます。

すべての `CTypedPtrList` 関数がインラインであるため、このテンプレートを使用してもコードのサイズや速度に大きな影響はありません。

から派生したリストは `CObList` シリアル化できますが、から派生したリストはシリアル化でき `CPtrList` ません。

`CTypedPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。

の使用方法の詳細については `CTypedPtrList` 、「アーティクル [コレクション](../../mfc/collections.md) と [テンプレートベースのクラス](../../mfc/template-based-classes.md)」を参照してください。

## <a name="example"></a>例

この例では、のインスタンスを作成し、1つのオブジェクトを追加して、 `CTypedPtrList` リストをディスクにシリアル化した後、オブジェクトを削除します。

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>要件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a> CTypedPtrList:: AddHead

このメンバー関数 `BASE_CLASS` **は、:: addhead** を呼び出します。

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
基底クラスリストに格納されている要素の型。

*(Newelement*<br/>
このリストに追加するオブジェクトポインター。 NULL 値が許可されます。

*BASE_CLASS*<br/>
型指定されたポインターリストクラスの基本クラスです。ポインターリストクラス ( [CObList](../../mfc/reference/coblist-class.md) または [CPtrList](../../mfc/reference/cptrlist-class.md)) である必要があります。

*pNewList*<br/>
別の [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) オブジェクトへのポインター。 *Pnewlist* 内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

### <a name="remarks"></a>解説

最初のバージョンでは、リストの先頭の前に新しい要素が追加されます。 2番目のバージョンは、先頭の前に別の要素のリストを追加します。

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a> CTypedPtrList:: AddTail

このメンバー関数 `BASE_CLASS` **は、:: addtail** を呼び出します。

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
基底クラスリストに格納されている要素の型。

*(Newelement*<br/>
このリストに追加するオブジェクトポインター。 NULL 値が許可されます。

*BASE_CLASS*<br/>
型指定されたポインターリストクラスの基本クラスです。ポインターリストクラス ( [CObList](../../mfc/reference/coblist-class.md) または [CPtrList](../../mfc/reference/cptrlist-class.md)) である必要があります。

*pNewList*<br/>
別の [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) オブジェクトへのポインター。 *Pnewlist* 内の要素が、この一覧に追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の位置の値を返します。

### <a name="remarks"></a>解説

最初のバージョンでは、リストの末尾の後に新しい要素が追加されます。 2番目のバージョンでは、リストの末尾の後に別の要素のリストが追加されます。

## <a name="ctypedptrlistgetat"></a><a name="getat"></a> CTypedPtrList:: GetAt

POSITION 型の変数は、リストのキーです。

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されている要素の型を指定するテンプレートパラメーター。

*position*<br/>
前の `GetHeadPosition` 関数または `Find` メンバー関数呼び出しによって返される位置の値。

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合、は、 `const CTypedPtrList` `GetAt` テンプレートパラメーター *型* によって指定された型のポインターを返します。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストが直接またはへのポインターによってアクセスされた場合、は、 `CTypedPtrList` `GetAt` テンプレートパラメーター *型* によって指定された型のポインターへの参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

インデックスとは異なり、位置の値を自分で操作することはできません。 `GetAt` 指定した `CObject` 位置に関連付けられているポインターを取得します。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

このインライン関数 `BASE_CLASS` **は、:: GetAt** を呼び出します。

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a> CTypedPtrList:: GetHead

このリストの head 要素を表すポインターを取得します。

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されている要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合、は、 `const CTypedPtrList` `GetHead` テンプレートパラメーター *型* によって指定された型のポインターを返します。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストが直接またはへのポインターによってアクセスされた場合、は、 `CTypedPtrList` `GetHead` テンプレートパラメーター *型* によって指定された型のポインターへの参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a> CTypedPtrList:: GetNext

*RPosition* によって識別されるリスト要素を取得し、 *rPosition* をリスト内の次のエントリの位置の値に設定します。

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
このリストに含まれる要素の型を指定するテンプレートパラメーター。

*rPosition*<br/>
前 `GetNext` の、 `GetHeadPosition` 、またはその他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合、は、 `const CTypedPtrList` `GetNext` テンプレートパラメーター *型* によって指定された型のポインターを返します。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストが直接またはへのポインターによってアクセスされた場合、は、 `CTypedPtrList` `GetNext` テンプレートパラメーター *型* によって指定された型のポインターへの参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

`GetNext` `GetHeadPosition` または[CPtrList:: Find](../../mfc/reference/coblist-class.md#find)を呼び出すことによって最初の位置を設定する場合は、前方反復ループでを使用できます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最後の要素である場合、 *rPosition* の新しい値は NULL に設定されます。

イテレーション中に要素を削除することができます。 「 [CObList:: RemoveAt](../../mfc/reference/coblist-class.md#removeat)」の例を参照してください。

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a> CTypedPtrList:: GetPrev

*RPosition* によって識別されるリスト要素を取得し、 *rPosition* をリスト内の前のエントリの位置の値に設定します。

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
このリストに含まれる要素の型を指定するテンプレートパラメーター。

*rPosition*<br/>
前の `GetPrev` または他のメンバー関数呼び出しによって返される位置値への参照。

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合、は、 `const CTypedPtrList` `GetPrev` テンプレートパラメーター *型* によって指定された型のポインターを返します。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストが直接またはへのポインターによってアクセスされた場合、は、 `CTypedPtrList` `GetPrev` テンプレートパラメーター *型* によって指定された型のポインターへの参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

またはの呼び出しを使用し `GetPrev` て初期位置を設定した場合は、逆反復ループでを使用でき `GetTailPosition` `Find` ます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

取得した要素がリスト内の最初の要素の場合、 *rPosition* の新しい値は NULL に設定されます。

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a> CTypedPtrList:: GetTail

このリストの head 要素を表すポインターを取得します。

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されている要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

へのポインターを使用してリストにアクセスした場合、は、 `const CTypedPtrList` `GetTail` テンプレートパラメーター *型* によって指定された型のポインターを返します。 これにより、関数を代入ステートメントの右側でのみ使用できるようになるため、リストが変更されないように保護できます。

リストが直接またはへのポインターによってアクセスされた場合、は、 `CTypedPtrList` `GetTail` テンプレートパラメーター *型* によって指定された型のポインターへの参照を返します。 これにより、関数を代入ステートメントのどちら側でも使用できるようになり、リストエントリを変更できるようになります。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `GetTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a> CTypedPtrList:: RemoveHead

リストの先頭から要素を削除し、その要素を返します。

```
TYPE RemoveHead();
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されている要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

リストの先頭にあるポインター。 このポインターは、テンプレートパラメーター *型* によって指定された型です。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveHead` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a> CTypedPtrList:: RemoveTail

リストの末尾から要素を削除し、その要素を返します。

```
TYPE RemoveTail();
```

### <a name="parameters"></a>パラメーター

*TYPE*<br/>
リストに格納されている要素の型を指定するテンプレートパラメーター。

### <a name="return-value"></a>戻り値

リストの末尾にあるポインター。 このポインターは、テンプレートパラメーター *型* によって指定された型です。

### <a name="remarks"></a>解説

を呼び出す前に、リストが空でないことを確認する必要があり `RemoveTail` ます。 リストが空の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistsetat"></a><a name="setat"></a> CTypedPtrList:: SetAt

このメンバー関数 `BASE_CLASS` **は、:: SetAt** を呼び出します。

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*TYPE*<br/>
基底クラスリストに格納されている要素の型。

*(Newelement*<br/>
リストに書き込まれるオブジェクトポインター。

### <a name="remarks"></a>解説

POSITION 型の変数は、リストのキーです。 インデックスとは異なり、位置の値を自分で操作することはできません。 `SetAt` リスト内の指定した位置にオブジェクトポインターを書き込みます。

位置の値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートされます。

詳細については、「 [CObList:: SetAt](../../mfc/reference/coblist-class.md#setat)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPtrList クラス](../../mfc/reference/cptrlist-class.md)<br/>
[CObList クラス](../../mfc/reference/coblist-class.md)
