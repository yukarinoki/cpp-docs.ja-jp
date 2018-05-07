---
title: コレクション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: beae5370c86bf0142b29f029778083f3042ae931
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="collections"></a>コレクション
Microsoft Foundation Class ライブラリでは、オブジェクトのグループを管理するコレクション クラスを提供します。 これらのクラスは、次の 2 種類があります。  
  
-   [C++ テンプレートから作成されるコレクション クラス](#_core_the_template_based_collection_classes)  
  
-   [テンプレートから作成されていないコレクション クラス](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  コードが既に非テンプレート コレクション クラスを使用する場合に使用する続行することができます。 独自のデータ型の新しいタイプ セーフなコレクション クラスを作成する場合は、新しいテンプレート ベースのクラスを使用することをお勧めします。  
  
##  <a name="_core_collection_shapes"></a> コレクションの形状  
 コレクション クラスは、その要素の種類とその"shape"で特徴付けられます。 図形は、オブジェクトが編成され、コレクションに格納する方法を参照します。 MFC には、次の 3 つの基本的なコレクションの形状が用意されています。 リスト、配列、および (ディクショナリとも呼ばれます) にマップします。 特定のプログラミングの問題に最も適していますコレクション形状を選択できます。  
  
 提供されたコレクションの 3 つの図形のそれぞれについては、このトピックの後半について簡単に説明します。 プログラムに最適な判断に役立つ図形の機能を比較するを参照してください。[コレクション クラスの選択に関する推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)です。  
  
-   リスト  
  
     List クラスはダブルリンク リストとして実装されている要素の順序付けられ、インデックス付けされていない一覧を示します。 一覧は、"head"、"tail"ありし、要素追加または削除、先頭または末尾、または挿入または削除、中間の要素は非常に高速です。  
  
-   配列  
  
     Array クラスは、オブジェクトの動的にサイズ設定された、順序付けられた、およびインデックスの整数の配列を提供します。  
  
-   マップ (ディクショナリとも呼ばれます)  
  
     マップは、コレクション オブジェクトを関連付ける、キー値オブジェクトです。  
  
##  <a name="_core_the_template_based_collection_classes"></a> テンプレート ベースのコレクション クラス  
 任意の型のオブジェクトを格納するタイプ セーフなコレクションを実装する最も簡単な方法では、テンプレート ベースの MFC クラスのいずれかを使用します。 これらのクラスの例については、MFC のサンプルを参照してください。[収集](../visual-cpp-samples.md)です。  
  
 次の表は、MFC のテンプレートに基づくコレクション クラスを一覧表示します。  
  
### <a name="collection-template-classes"></a>テンプレートのコレクション クラス  
  
|コレクションの内容|配列|表示内容|マップ|  
|-------------------------|------------|-----------|----------|  
|任意の型のオブジェクトのコレクション|`CArray`|`CList`|`CMap`|  
|任意の型のオブジェクトへのポインターのコレクション|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> テンプレートに基づいていないコレクション クラス  
 アプリケーションで既に MFC 非テンプレート クラスを使用する場合に使用する続行することができます。 ただし、新しいコレクションの場合は、テンプレート ベースのクラスを使用する勧めします。 次の表では、MFC コレクション クラスをテンプレートに基づいていないを一覧表示します。  
  
### <a name="nontemplate-collection-classes"></a>非テンプレート コレクション クラス  
  
|配列|表示内容|マップ|  
|------------|-----------|----------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 MFC コレクション クラスの特性がテーブルに[コレクション クラスの選択に関する推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)これらの特性 (形状) 以外の観点からの MFC コレクション クラスについて説明します。  
  
-   クラスで C++ テンプレートを使用しているかどうか  
  
-   コレクションに格納されている要素をシリアル化できるかどうか  
  
-   コレクションに格納されている要素を診断用にダンプできるかどうか  
  
-   タイプ セーフなコレクションかどうか  
  
### <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
#### <a name="general-collection-class-tasks"></a>コレクション クラスの一般的なタスク  
  
-   [コレクション クラスの選択に関する推奨事項](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [方法: タイプ セーフなコレクションを作成する](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [スタック コレクションとキュー コレクションの作成](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../mfc/reference/carray-class.md#add)  
  
#### <a name="template-based-collection-class-tasks"></a>テンプレート ベースのコレクション クラスの操作  
  
-   [テンプレート ベースのクラス](../mfc/template-based-classes.md)  
  
#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>コレクションのメンバーへのアクセス (テンプレートに基づくか)  
  
-   [コレクションの全メンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [CObject コレクションの全オブジェクトの削除](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

