---
title: テンプレート ベースのクラス
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 29f5f815b62835aedbca1f79b797f826ea53d83b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370453"
---
# <a name="template-based-classes"></a>テンプレート ベースのクラス

この資料では、MFC バージョン 3.0 以降のタイプ セーフなテンプレート ベースのコレクション クラスについて説明します。 これらのテンプレートを使用してタイプ セーフなコレクションを作成する方が便利で、テンプレートに基づくコレクション クラスを使用するよりも効果的にタイプ セーフを提供できます。

MFC では、テンプレート ベースのコレクションの 2 つのカテゴリを事前に定義します。

- [シンプルな配列、リスト、マップのクラス](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [型指定されたポインターの配列、リスト、およびマップ](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

単純なコレクション クラスはすべて クラス`CObject`から派生しているため、シリアル化、動的作成、およびその他のプロパティ`CObject`を継承します。 型指定されたポインター コレクション クラスでは、派生元のクラスを指定する必要があります`CPtrList``CPtrArray`。 新しいコレクション クラスは指定された基本クラスを継承し、新しいクラスのメンバー関数は、タイプ セーフを適用するために、基本クラスのメンバーへのカプセル化された呼び出しを使用します。

C++ テンプレートの詳細については *、『C++ 言語リファレンス*』の[「テンプレート](../cpp/templates-cpp.md)」を参照してください。

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>単純な配列、リスト、およびマップ テンプレートの使用

単純なコレクション テンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクション宣言で使用するパラメーターを把握する必要があります。

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a>単純な配列とリストの使用

単純な配列とリスト クラス[CArray](../mfc/reference/carray-class.md)と[CList](../mfc/reference/clist-class.md)は *、TYPE*と`ARG_TYPE`TYPE の 2 つのパラメータを受け取ります。 これらのクラスには *、TYPE*パラメーターで指定する任意のデータ型を格納できます。

- 基本的な C++ データ型 **(int** **、char**、float など **)**

- C++ の構造体とクラス

- 定義するその他のタイプ

便宜上、効率を高めるために *、ARG_TYPE*パラメータを使用して関数の引数の型を指定できます。 通常 *、TYPE*パラメーターで指定した型への参照として*ARG_TYPE*を指定します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

最初の例では`myArray`**、int**s を含む配列コレクションを宣言します。 2 番目の例では、`myList`オブジェクトを格納`CPerson`するリスト コレクション を宣言します。 コレクション クラスの特定のメンバー関数は *、ARG_TYPE*テンプレート パラメーターで指定された型の引数を受け取ります。 たとえば、クラス`CArray`の`Add`メンバー関数は *、ARG_TYPE*引数を受け取ります。

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a>単純なマップの使用

単純なマップ クラス[CMap](../mfc/reference/cmap-class.md)には *、KEY* *、ARG_KEY*、*値*、および*ARG_VALUE*の 4 つのパラメータが使用されます。 配列クラスやリスト クラスと同様に、map クラスは任意のデータ型を格納できます。 格納するデータのインデックスと順序付けが行われる配列やリストとは異なり、関連付けるキーと値をマップします。 *KEY*パラメーターは、マップに格納されているデータにアクセスするために使用されるキーのデータ型を指定します。 *KEY*の型が構造体またはクラスの場合 *、ARG_KEY*パラメータは通常 *、KEY*で指定された型への参照です。 *VALUE*パラメーターは、マップに格納されている項目のタイプを指定します。 *ARG_VALUE*の型が構造体またはクラスの場合、*通常、ARG_VALUE*パラメータは*VALUE*で指定された型への参照です。 次に例を示します。

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

最初の例では`MY_STRUCT`、値を格納し **、int**キーでアクセスし`MY_STRUCT`、参照によってアクセスされたアイテムを返します。 2 番目の`CPerson`例では、値を格納`CString`し、キーでアクセスし、アクセスされたアイテムへの参照を返します。 この例では、姓で人を検索する単純なアドレス帳を表している場合があります。

*KEY*パラメータは型`CString`で *、KEY_TYPE*パラメータは型`LPCSTR`であるため、キーは型のアイテムとしてマップに格納されますが、型`CString`のポインターなど`SetAt`で参照される関数で参照されます。 `LPCSTR` 次に例を示します。

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a>型指定されたポインター コレクション テンプレートの使用

型指定されたポインターコレクション テンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクション宣言で使用するパラメーターを把握する必要があります。

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a>型付きポインター配列とリストの使用法

型指定されたポインター配列とリスト クラス[の CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md)と[CTypedPtrList](../mfc/reference/ctypedptrlist-class.md)は *、BASE_CLASS*と TYPE の 2 つのパラメーターを受け取*ります*。 これらのクラスには *、TYPE*パラメーターで指定した任意のデータ型を格納できます。 ポインターを格納する非テンプレート コレクション クラスの 1 つから派生します。この基本クラスは*BASE_CLASS*で指定します。 配列の場合は、`CObArray`または`CPtrArray`を使用します。 リストの場合は、 `CObList` `CPtrList`または を使用します。

実際には、たとえば`CObList`、基底クラスに基づいてコレクションを宣言すると、その基本クラスのメンバーを継承するだけでなく、基本クラスのメンバーへの呼び出しをカプセル化することでタイプ セーフな型セーフを提供する多数の追加のタイプ セーフメンバー関数および演算子も宣言します。 これらのカプセル化は、必要なすべての型変換を管理します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

最初の例では、型指定されたポインター配列`myArray`を宣言`CObArray`します。 配列は、オブジェクト (`CPerson`クラス`CPerson`から派生した) へのポインターを格納`CObject`および返します。 任意のメンバー関数`CObArray`を呼び出すか、新しいタイプ セーフ`GetAt`関数と`ElementAt`関数を呼び出すか、タイプ セーフな [ **]** 演算子を使用できます。

2 番目の例では、型指定されたポインター`myList`リスト`CPtrList`を宣言します。 リストは、オブジェクトへの`MY_STRUCT`ポインタを格納し、返します。 に`CPtrList`基づくクラスは、 から`CObject`派生していないオブジェクトへのポインターを格納するために使用されます。 `CTypedPtrList`には、タイプ セーフなメンバ関数が多数`GetHead``GetPrev``GetAt`あります`GetTail`。 `RemoveHead` `RemoveTail` `GetNext`

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a>型指定されたポインター マップの使用法

型指定されたポインター マップ クラス[CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md)は *、BASE_CLASS、KEY*、および VALUE の 3 つのパラメータを受け取*ります*。 *KEY* *BASE_CLASS*パラメーターは、新`CMapPtrToWord`しいクラス 、 、 `CMapPtrToPtr`、 `CMapStringToPtr` `CMapWordToPtr`、`CMapStringToOb`など派生元のクラスを指定します。 *KEY*は KEY*に類似*`CMap`しています : ルックアップに使用されるキーのタイプを指定します。 *VALUE*は *、VALUE* in`CMap`に類似しています: マップに格納されているオブジェクトのタイプを指定します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

最初の例は、に基づく`CMapPtrToPtr`マップです`CString`— ポインタにマップされたキー`MY_STRUCT`を使用します。 タイプ セーフ`Lookup`なメンバー関数を呼び出すことによって、格納されたポインターを検索できます。 **[ ]** 演算子を使用して、格納されているポインターを検索し、見つからない場合は追加できます。 また、タイプ セーフ`GetNextAssoc`関数を使用してマップを反復処理することもできます。 クラスの他のメンバー関数を呼び`CMapPtrToPtr`出すこともできます。

2 番目の例は、オブジェクト`CMapStringToOb`への格納されたポインターにマップされた文字列キーを使用する`CMyObject`マップです。 前の段落で説明したタイプ セーフメンバを使用することも、class`CMapStringToOb`のメンバを呼び出すことができます。

> [!NOTE]
> 型へのポインターや参照ではなく *、VALUE*パラメーターに**クラス**または**構造体**の型を指定する場合、クラスまたは構造体にコピー コンストラクターが必要です。

詳細については、「[タイプ セーフなコレクションを作成する方法](../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コレクション](../mfc/collections.md)
