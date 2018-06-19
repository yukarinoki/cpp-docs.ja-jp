---
title: クラスのテンプレートに基づく |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68d44a66f328465f2c59fb361f9bb6b2a76efa82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385474"
---
# <a name="template-based-classes"></a>テンプレート ベースのクラス
この記事では、MFC バージョン 3.0 以降ではタイプ セーフなテンプレート ベースのコレクション クラスについて説明します。 これらのテンプレートを使用して、タイプ セーフなコレクションを作成する方が便利なタイプ セーフをテンプレートに基づいていないコレクション クラスを使用するよりも効率的に実現します。  
  
 MFC では、テンプレート ベースのコレクションの 2 つのカテゴリをでください。  
  
-   [単純な配列、リスト、およびマップ クラス](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`、`CList`、`CMap`  
  
-   [配列、リスト、および型指定されたポインターのマップ](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`、`CTypedPtrList`、`CTypedPtrMap`  
  
 単純なコレクション クラスのすべてのクラスから派生`CObject`シリアル化、動的な作成、およびその他のプロパティが継承されるよう、`CObject`です。 型付きポインター コレクション クラスから派生するクラスを指定する必要があります: などの MFC で定義済みテンプレート ポインター コレクションのいずれかを指定する必要があります`CPtrList`または`CPtrArray`です。 コレクション クラスが、指定した基本クラスから継承し、新しいクラスのメンバー関数では、カプセル化されたメンバーの呼び出しを基本クラスを使用して、タイプ セーフを適用します。  
  
 C++ テンプレートの詳細については、次を参照してください。[テンプレート](../cpp/templates-cpp.md)で、 *C++ 言語リファレンス*です。  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> 単純な配列、リスト、およびマップ テンプレートを使用します。  
 単純なコレクションのテンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクションを宣言で使用するには、どのようなパラメーターを確認する必要があります。  
  
###  <a name="_core_simple_array_and_list_usage"></a> 単純な配列とリストの使い方  
 単純な配列とリスト クラス[CArray](../mfc/reference/carray-class.md)と[CList](../mfc/reference/clist-class.md)、2 つのパラメーター:*型*と`ARG_TYPE`です。 これらのクラスがで指定した任意のデータ型を格納できる、*型*パラメーター。  
  
-   などの基本的な C++ のデータ型`int`、 `char`、および**float**  
  
-   C++ 構造体とクラス  
  
-   他の型を定義します。  
  
 利便性と効率性は、使用することができます、`ARG_TYPE`パラメーターを関数の引数の型を指定します。 通常は指定`ARG_TYPE`で名前を付けた型への参照として、*型*パラメーター。 例えば:  
  
 [!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]  
  
 最初の例では、配列のコレクション、`myArray`を格納している`int`s。 2 番目の例では、宣言のリスト コレクション`myList`、格納する`CPerson`オブジェクト。 コレクション クラスのメンバー関数は、によって指定された型の引数を受け取る、`ARG_TYPE`テンプレート パラメーター。 たとえば、**追加**クラスのメンバー関数`CArray`受け取り、`ARG_TYPE`引数。  
  
 [!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]  
  
###  <a name="_core_simple_map_usage"></a> 単純なマップの使用方法  
 単純なマップ クラス[CMap](../mfc/reference/cmap-class.md)、4 つのパラメーターを受け取る:*キー*、 `ARG_KEY`、*値*、および`ARG_VALUE`です。 クラスと同様に、配列とリスト、マップ クラスは、任意のデータ型を格納できます。 配列と列がインデックスを格納しているデータの順序付け、リストとは異なりマップを関連付けるキーと値。 値の関連付けられたキーを指定することで、マップに格納されている値にアクセスします。 *キー*パラメーターがマップに格納されているデータへのアクセスに使用されるキーのデータ型を指定します。 場合の種類*キー*構造体またはクラスでは、`ARG_KEY`パラメーターで指定された型への参照では通常*キー*です。 *値*パラメーターがマップに格納されている項目の種類を指定します。 場合の種類`ARG_VALUE`構造体またはクラスでは、`ARG_VALUE`パラメーターで指定された型への参照では通常*値*です。 例えば:  
  
 [!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]  
  
 最初の例ストア`MY_STRUCT`値は、によってそれらにアクセスする`int`キー、およびアクセスを返します`MY_STRUCT`参照によって項目。 2 番目の例ストア`CPerson`値は、によってそれらにアクセスする`CString`キーを押し、アクセスされるアイテムへの参照を返します。 この例を検索する人物を姓で、単純なアドレス帳を表す場合があります。  
  
 *キー*パラメーターの型は`CString`と*KEY_TYPE*パラメーターの型は`LPCSTR`、型の項目として、マップ内のキーが格納されている`CString`で参照されるが、などの関数`SetAt`型のポインターによって`LPCSTR`です。 例えば:  
  
 [!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> 型付きポインター コレクションのテンプレートを使用します。  
 型付きポインター コレクション テンプレートを使用するには、これらのコレクションに格納できるデータの種類と、コレクションを宣言で使用するには、どのようなパラメーターを確認する必要があります。  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> 型付きポインター配列とリストの使い方  
 型付きポインター配列とリスト クラス[CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md)と[CTypedPtrList](../mfc/reference/ctypedptrlist-class.md)、2 つのパラメーター:`BASE_CLASS`と*型*です。 これらのクラスがで指定した任意のデータ型を格納できる、*型*パラメーター。 ポインターを格納する、非テンプレート コレクション クラスのいずれかから派生しています。この基本クラスを指定する`BASE_CLASS`です。 アレイのどちらも使用`CObArray`または`CPtrArray`です。 リストについては、いずれかの操作を使用して`CObList`または`CPtrList`です。  
  
 実際には、基にしたコレクションを宣言する場合と`CObList`新しいクラスがだけでなく、その基本クラスのメンバーを継承しますが、その他のタイプ セーフなメンバー関数とカプセル化することによってタイプ セーフを確保するのに役立ちます演算子も宣言、基本クラスのメンバーの呼び出し。 これらをカプセル化は、すべての必要な型変換を管理します。 例えば:  
  
 [!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]  
  
 最初の例で、型付きポインター配列`myArray`から派生した`CObArray`です。 配列が格納およびへのポインターを返す`CPerson`オブジェクト (ここで`CPerson`はから派生したクラス`CObject`)。 呼び出す`CObArray`メンバー関数、またはするには、新しいタイプ セーフを呼び出すことができます`GetAt`と`ElementAt`関数やタイプ セーフを使用して **[ ]** 演算子。  
  
 2 番目の例では、宣言、型付きポインター リスト`myList`から派生した`CPtrList`です。 一覧が格納およびへのポインターを返す`MY_STRUCT`オブジェクト。 クラスがに基づいて`CPtrList`から派生していないオブジェクトへのポインターを格納するために使用`CObject`です。 `CTypedPtrList` タイプ セーフなメンバー関数の数を持つ: `GetHead`、 `GetTail`、 `RemoveHead`、 `RemoveTail`、 `GetNext`、 `GetPrev`、および`GetAt`です。  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a> 型指定されたポインターのマップの使用方法  
 型指定されたポインター マップ クラス[CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md)、3 つのパラメーターを受け取る: `BASE_CLASS`、*キー*、および*値*です。 `BASE_CLASS`パラメーターは、新しいクラスを派生元のクラスを指定: `CMapPtrToWord`、 `CMapPtrToPtr`、 `CMapStringToPtr`、 `CMapWordToPtr`、`CMapStringToOb`のようにします。 *キー*に似ています*キー*で`CMap`: 参照に使用されるキーの種類を指定します。 *値*に似ています*値*で`CMap`: マップに格納されているオブジェクトの種類を指定します。 例えば:  
  
 [!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]  
  
 最初の例は、マップに基づく**CMapPtrToPt**r: を使用して`CString`へのポインターへのマップ キー`MY_STRUCT`です。 タイプ セーフを呼び出すことによって、格納されているポインターを検索できます`Lookup`メンバー関数。 使用することができます、 **[ ]** 演算子に格納されているポインターを検索し、追加することがない場合。 タイプ セーフを使用してマップを反復処理できると`GetNextAssoc`関数。 呼び出すことができますも他のメンバー クラスの関数は`CMapPtrToPtr`します。  
  
 2 番目の例に基づくマップ**CMapStringToO**b — ストアド ポインターにマップされている文字列のキーを使用して`CMyObject`オブジェクト。 前の段落で説明されている同じタイプ セーフなメンバーを使用するか、クラスのメンバーを呼び出すことができます`CMapStringToOb`です。  
  
> [!NOTE]
>  指定した場合、**クラス**または`struct`の入力、*値*パラメーターではなくポインターまたは種類、クラスまたは構造体への参照がコピー コンス トラクターを持つ必要があります。  
  
 詳細については、次を参照してください。[タイプ セーフなコレクションを作成する方法](../mfc/how-to-make-a-type-safe-collection.md)です。  
  
## <a name="see-also"></a>関連項目  
 [コレクション](../mfc/collections.md)

