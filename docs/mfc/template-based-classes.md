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
ms.openlocfilehash: eceee4421b43515b9b246f4af26a1a3741c6b25b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230455"
---
# <a name="template-based-classes"></a>テンプレート ベースのクラス

この記事では、MFC バージョン3.0 以降のタイプセーフなテンプレートベースのコレクションクラスについて説明します。 これらのテンプレートを使用してタイプセーフなコレクションを作成する方が便利で、テンプレートに基づいていないコレクションクラスを使用するよりも、型の安全性をより効果的に提供できます。

MFC 事前には、テンプレートベースのコレクションの2つのカテゴリがあります。

- [単純な配列、リスト、およびマップクラス](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [型指定されたポインターの配列、リスト、およびマップ](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

単純なコレクションクラスはすべてクラスから派生するので、 `CObject` のシリアル化、動的な作成、およびその他のプロパティを継承し `CObject` ます。 型指定されたポインターコレクションクラスでは、派生元のクラスを指定する必要があります。これは、やなど、MFC によって定義済みの非テンプレートポインターコレクションのいずれかである必要があり `CPtrList` `CPtrArray` ます。 新しいコレクションクラスは、指定された基底クラスを継承し、新しいクラスのメンバー関数は、基底クラスのメンバーへのカプセル化された呼び出しを使用して、タイプセーフを適用します。

C++ テンプレートの詳細については、「 *C++ 言語リファレンス*」の「[テンプレート](../cpp/templates-cpp.md)」を参照してください。

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>単純な配列、リスト、マップテンプレートの使用

単純なコレクションテンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクション宣言で使用するパラメーターを把握しておく必要があります。

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a>単純な配列とリストの使用法

単純な配列クラスとリストクラス[CArray](../mfc/reference/carray-class.md)と[CList](../mfc/reference/clist-class.md)では *、との*2 つのパラメーターを受け取ります。 `ARG_TYPE` これらのクラスは、*型*パラメーターで指定する任意のデータ型を格納できます。

- 、、などの基本的な C++ データ型 **`int`** **`char`****`float`**

- C++ の構造体とクラス

- 定義するその他の型

利便性と効率性を高めるために、 *ARG_TYPE*パラメーターを使用して関数の引数の型を指定できます。 通常は、*型*パラメーターで指定した型への参照として*ARG_TYPE*を指定します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

最初の例では、を含む配列コレクションを宣言して `myArray` **`int`** います。 2番目の例では、オブジェクトを格納するリストコレクションを宣言し `myList` `CPerson` ます。 コレクションクラスの特定のメンバー関数は、 *ARG_TYPE*テンプレートパラメーターによって型が指定された引数を受け取ります。 たとえば、 `Add` クラスのメンバー関数は、 `CArray` *ARG_TYPE*の引数を受け取ります。

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a>単純なマップの使用法

単純なマップクラス[CMap](../mfc/reference/cmap-class.md)は、*キー*、 *ARG_KEY*、*値*、 *ARG_VALUE*の4つのパラメーターを受け取ります。 配列クラスやリストクラスと同様に、マップクラスは任意のデータ型を格納できます。 格納するデータのインデックスと順序を指定する配列やリストとは異なり、マップにはキーと値を関連付けるために、値に関連付けられているキーを指定することによってマップに格納されている値にアクセスします。 *KEY*パラメーターは、マップに格納されているデータにアクセスするために使用されるキーのデータ型を指定します。 *キー*の型が構造体またはクラスの場合、通常、 *ARG_KEY*パラメーターは、 *key*で指定された型への参照です。 *値*パラメーターは、マップに格納されている項目の種類を指定します。 *ARG_VALUE*の型が構造体またはクラスの場合、通常、 *ARG_VALUE*パラメーターは*VALUE*で指定された型への参照です。 次に例を示します。

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

最初の例では、 `MY_STRUCT` 値を格納し、キーによってアクセス **`int`** し、アクセスされた `MY_STRUCT` 項目を参照渡しで返します。 2番目の例では、 `CPerson` 値を格納し、キーによってアクセス `CString` し、アクセスされた項目への参照を返します。 この例では、姓によって人物を検索する単純なアドレス帳を表す場合があります。

*キー*パラメーターが型であり、 `CString` *KEY_TYPE*パラメーターが型であるため `LPCSTR` 、キーは型の項目としてマップに格納され `CString` ますが、型のポインターによってなどの関数で参照され `SetAt` `LPCSTR` ます。 次に例を示します。

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a>型指定されたポインターのコレクションテンプレートの使用

型指定されたポインターのコレクションテンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクション宣言で使用するパラメーターを把握しておく必要があります。

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a>型指定されたポインターの配列とリストの使用法

型指定されたポインターの配列とリストクラス[CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md)と[CTypedPtrList](../mfc/reference/ctypedptrlist-class.md)は、 *BASE_CLASS*と*型*の2つのパラメーターを受け取ります。 これらのクラスは、*型*パラメーターで指定する任意のデータ型を格納できます。 これらは、ポインターを格納する非テンプレートコレクションクラスの1つから派生します。この基本クラスは*BASE_CLASS*で指定します。 配列の場合は、 `CObArray` またはを使用し `CPtrArray` ます。 リストについては、またはを使用し `CObList` `CPtrList` ます。

実際には、に基づいてコレクションを宣言すると、 `CObList` 新しいクラスがその基底クラスのメンバーを継承するだけでなく、さらに多くのタイプセーフなメンバー関数と演算子も宣言し、基底クラスのメンバーへの呼び出しをカプセル化することによってタイプセーフを提供することができます。 これらのカプセル化は、必要なすべての型変換を管理します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

最初の例では、から派生した型指定されたポインター配列を宣言して `myArray` `CObArray` います。 配列は、 `CPerson` オブジェクト ( `CPerson` はから派生したクラス) へのポインターを格納し、返し `CObject` ます。 任意のメンバー関数を呼び出すことができ `CObArray` ます。または、新しいタイプセーフ関数と関数を呼び出すことも、 `GetAt` `ElementAt` タイプセーフな **[]** 演算子を使用することもできます。

2番目の例では、から派生した型指定されたポインターのリストを宣言して `myList` `CPtrList` います。 リストは、オブジェクトへのポインターを格納し、返し `MY_STRUCT` ます。 に基づくクラスは、 `CPtrList` から派生していないオブジェクトへのポインターを格納するために使用され `CObject` ます。 `CTypedPtrList`には、、、、、、、 `GetHead` `GetTail` `RemoveHead` `RemoveTail` `GetNext` `GetPrev` およびと `GetAt` いうタイプセーフなメンバー関数が多数あります。

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a>型指定されたポインターマップの使用法

型指定されたポインターのマップクラス[CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md)は、 *BASE_CLASS*、*キー*、および*値*の3つのパラメーターを受け取ります。 *BASE_CLASS*パラメーターは、新しいクラスの派生元のクラス (、、、、など) を指定し `CMapPtrToWord` `CMapPtrToPtr` `CMapStringToPtr` `CMapWordToPtr` `CMapStringToOb` ます。 *キー*はの*キー*に似 `CMap` ています。これは、参照に使用されるキーの種類を指定します。 *値*はの*値*に似ています。 `CMap` map に格納されているオブジェクトの種類を指定します。 次に例を示します。

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

最初の例は、に基づくマップで、 `CMapPtrToPtr` へのポインターにマップされたキーを使用 `CString` `MY_STRUCT` します。 型セーフなメンバー関数を呼び出すことによって、格納されているポインターを検索でき `Lookup` ます。 **[]** 演算子を使用して、格納されているポインターを検索し、見つからない場合は追加できます。 また、タイプセーフな関数を使用してマップを反復処理でき `GetNextAssoc` ます。 クラスの他のメンバー関数を呼び出すこともでき `CMapPtrToPtr` ます。

2番目の例は、に基づくマップで、 `CMapStringToOb` オブジェクトへの格納されたポインターにマップされる文字列キーを使用 `CMyObject` します。 前の段落で説明したのと同じタイプセーフメンバーを使用することも、クラスのメンバーを呼び出すこともでき `CMapStringToOb` ます。

> [!NOTE]
> **`class`** **`struct`** 型へのポインターまたは参照ではなく、*値*パラメーターにまたは型を指定する場合は、クラスまたは構造体にコピーコンストラクターが必要です。

詳細については、「[タイプセーフなコレクションを作成する方法](../mfc/how-to-make-a-type-safe-collection.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コレクション](../mfc/collections.md)
