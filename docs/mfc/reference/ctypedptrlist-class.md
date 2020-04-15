---
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
ms.openlocfilehash: 40dbfb822e71309e9675aba14d46d333ffa4ee06
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373262"
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
型指定されたポインター リスト クラスの基本クラス。ポインター リスト クラス ( `CObList` `CPtrList`または ) である必要があります。

*種類*<br/>
基本クラスのリストに格納されている要素の型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クタイプドレットリスト::AddHead](#addhead)|リストの先頭に要素 (または別のリストのすべての要素) を追加します (新しいヘッドを作成)。|
|[クタイプドレットリスト::AddTail](#addtail)|リストの末尾に要素 (または別のリストのすべての要素) を追加します (新しい末尾になります)。|
|[クタイププターリスト::ゲットアット](#getat)|指定した位置にある要素を取得します。|
|[クタイプ付きプサーリスト::ゲットヘッド](#gethead)|リストの head 要素を返します (空にすることはできません)。|
|[次のリストを取得します。](#getnext)|反復処理の次の要素を取得します。|
|[クタイプドレットリスト::ゲットプレフ](#getprev)|反復処理の前の要素を取得します。|
|[クタイププターリスト::ゲットテール](#gettail)|リストの末尾要素を返します (空にすることはできません)。|
|[クタイプ付きのプターリスト::削除ヘッド](#removehead)|リストの先頭から要素を削除します。|
|[クタイプ付きPtrリスト::リムープテール](#removetail)|リストの末尾から要素を削除します。|
|[クタイプ付きのプットリスト::セットアット](#setat)|指定した位置に要素を設定します。|

## <a name="remarks"></a>解説

または`CPtrList`ではなく`CTypedPtrList``CObList`を使用する場合、C++ 型検査機能は、ポインター型の不一致によって発生するエラーを除去するのに役立ちます。

さらに、ラッパーは`CTypedPtrList`、使用する場合に必要となるキャスティングの多くを実行`CObList`します。 `CPtrList`

すべての`CTypedPtrList`関数がインラインであるため、このテンプレートを使用しても、コードのサイズや速度に大きな影響はありません。

から`CObList`派生したリストはシリアル化できますが、派生`CPtrList`したリストはシリアル化できません。

`CTypedPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。

の使用方法`CTypedPtrList`の詳細については、「 コレクションと[テンプレート ベースのクラス](../../mfc/template-based-classes.md)」を参照してください。 [Collections](../../mfc/collections.md)

## <a name="example"></a>例

この例では、 の`CTypedPtrList`インスタンスを作成し、1 つのオブジェクトを追加し、リストをディスクにシリアル化してから、オブジェクトを削除します。

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a>クタイプドレットリスト::AddHead

このメンバー関数は`BASE_CLASS`**、::AddHead**を呼び出します。

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
基本クラスのリストに格納されている要素の型。

*新しい要素*<br/>
このリストに追加するオブジェクト ポインター。 NULL 値を使用できます。

*BASE_CLASS*<br/>
型指定されたポインター リスト クラスの基本クラス。ポインター リスト クラス ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md)) である必要があります。

*をクリックします。*<br/>
別の[CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクトへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

### <a name="remarks"></a>解説

最初のバージョンでは、リストの先頭の前に新しい要素が追加されます。 2 番目のバージョンでは、ヘッドの前に要素の別のリストを追加します。

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a>クタイプドレットリスト::AddTail

このメンバー関数は`BASE_CLASS`**、::AddTail**を呼び出します。

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
基本クラスのリストに格納されている要素の型。

*新しい要素*<br/>
このリストに追加するオブジェクト ポインター。 NULL 値を使用できます。

*BASE_CLASS*<br/>
型指定されたポインター リスト クラスの基本クラス。ポインター リスト クラス ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md)) である必要があります。

*をクリックします。*<br/>
別の[CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクトへのポインター。 *pNewList*の要素がこのリストに追加されます。

### <a name="return-value"></a>戻り値

最初のバージョンは、新しく挿入された要素の POSITION 値を返します。

### <a name="remarks"></a>解説

最初のバージョンでは、リストの末尾の後に新しい要素が追加されます。 2 番目のバージョンでは、リストの末尾の後に別の要素のリストが追加されます。

## <a name="ctypedptrlistgetat"></a><a name="getat"></a>クタイププターリスト::ゲットアット

POSITION 型の変数は、リストのキーです。

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されている要素の型を指定するテンプレート パラメーター。

*位置*<br/>
前`GetHeadPosition`の関数呼び出しまたは`Find`メンバー関数呼び出しによって返される POSITION 値。

### <a name="return-value"></a>戻り値

リストにアクセスするときに、 へのポインターを使用`const CTypedPtrList`して`GetAt`アクセスした場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターを返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CTypedPtrList`介してアクセスした`GetAt`場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターへの参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 `GetAt`指定された位置`CObject`に関連付けられたポインターを取得します。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

このインライン関数は`BASE_CLASS`**、::GetAt**を呼び出します。

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a>クタイプ付きプサーリスト::ゲットヘッド

このリストの head 要素を表すポインターを取得します。

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されている要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

リストにアクセスするときに、 へのポインターを使用`const CTypedPtrList`して`GetHead`アクセスした場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターを返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CTypedPtrList`介してアクセスした`GetHead`場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターへの参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

を呼び出す`GetHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a>次のリストを取得します。

*rPosition*で識別されるリスト要素を取得し *、rPosition*をリスト内の次のエントリの POSITION 値に設定します。

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
このリストに含まれる要素の型を指定するテンプレート パラメーター。

*r位置*<br/>
前`GetNext`の 、 、`GetHeadPosition`または他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

リストにアクセスするときに、 へのポインターを使用`const CTypedPtrList`して`GetNext`アクセスした場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターを返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CTypedPtrList`介してアクセスした`GetNext`場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターへの参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

または`GetNext`[CPtrList::Find](../../mfc/reference/coblist-class.md#find)を呼び出して初期位置を`GetHeadPosition`確立する場合は、順方向反復ループで使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最後の要素である場合 *、rPosition*の新しい値は NULL に設定されます。

反復中に要素を削除することができます。 [「CObList::RemoveAt」](../../mfc/reference/coblist-class.md#removeat)の例を参照してください。

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a>クタイプドレットリスト::ゲットプレフ

*rPosition*で識別されるリスト要素を取得し *、rPosition*をリスト内の前のエントリの POSITION 値に設定します。

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
このリストに含まれる要素の型を指定するテンプレート パラメーター。

*r位置*<br/>
前`GetPrev`のメンバー関数呼び出しまたは他のメンバー関数呼び出しによって返された POSITION 値への参照。

### <a name="return-value"></a>戻り値

リストにアクセスするときに、 へのポインターを使用`const CTypedPtrList`して`GetPrev`アクセスした場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターを返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CTypedPtrList`介してアクセスした`GetPrev`場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターへの参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

または への`GetPrev`呼び出し`GetTailPosition`で初期位置を確立する場合は、逆反復ループ`Find`で使用できます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得した要素がリストの最初の要素である場合 *、rPosition*の新しい値は NULL に設定されます。

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a>クタイププターリスト::ゲットテール

このリストの head 要素を表すポインターを取得します。

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されている要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

リストにアクセスするときに、 へのポインターを使用`const CTypedPtrList`して`GetTail`アクセスした場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターを返します。 これにより、関数は代入ステートメントの右側でのみ使用できるため、リストが変更されないように保護されます。

リストに直接アクセスするか、 へのポインターを`CTypedPtrList`介してアクセスした`GetTail`場合は、 テンプレート パラメーター *TYPE*で指定された型のポインターへの参照を返します。 これにより、代入ステートメントの両側で関数を使用できるため、リストエントリを変更できます。

### <a name="remarks"></a>解説

を呼び出す`GetTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a>クタイプ付きのプターリスト::削除ヘッド

リストの先頭から要素を削除し、返します。

```
TYPE RemoveHead();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されている要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

以前のリストの先頭にあるポインター。 このポインターは、テンプレート・パラメーター *TYPE*で指定された型です。

### <a name="remarks"></a>解説

を呼び出す`RemoveHead`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a>クタイプ付きPtrリスト::リムープテール

リストの末尾から要素を削除し、返します。

```
TYPE RemoveTail();
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
リストに格納されている要素の型を指定するテンプレート パラメーター。

### <a name="return-value"></a>戻り値

以前のリストの末尾にあるポインター。 このポインターは、テンプレート・パラメーター *TYPE*で指定された型です。

### <a name="remarks"></a>解説

を呼び出す`RemoveTail`前に、リストが空でないことを確認する必要があります。 リストが空の場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 [IsEmpty](../../mfc/reference/coblist-class.md#isempty)を使用して、リストに要素が含まれていることを確認します。

## <a name="ctypedptrlistsetat"></a><a name="setat"></a>クタイプ付きのプットリスト::セットアット

このメンバー関数は`BASE_CLASS`**、::SetAt**を呼び出します。

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
設定する要素の位置。

*種類*<br/>
基本クラスのリストに格納されている要素の型。

*新しい要素*<br/>
リストに書き込まれるオブジェクト ポインター。

### <a name="remarks"></a>解説

POSITION 型の変数は、リストのキーです。 これはインデックスと同じではなく、POSITION 値を自分で操作することはできません。 `SetAt`リスト内の指定した位置にオブジェクト ポインタを書き込みます。

POSITION 値がリスト内の有効な位置を表していることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

詳細な説明については[、「CObList::SetAt」](../../mfc/reference/coblist-class.md#setat)を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CPtrList クラス](../../mfc/reference/cptrlist-class.md)<br/>
[CObList クラス](../../mfc/reference/coblist-class.md)
