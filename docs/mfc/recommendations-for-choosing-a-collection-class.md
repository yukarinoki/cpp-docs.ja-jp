---
title: コレクション クラスの選択に関する推奨事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type safety of collection classes [MFC]
- collection classes [MFC], serialization
- collection classes [MFC], speed
- collection classes [MFC], type safety
- collection classes [MFC], choosing
- collection classes [MFC], functionality
- shapes, collection
- collection classes [MFC], template-based
- MFC collection classes [MFC], characteristics
- collection classes [MFC], about collection classes [MFC]
- serialization [MFC], collection classes
- collection classes [MFC], duplicates allowed
- collection classes [MFC], shapes
ms.assetid: a82188cd-443f-40d8-a244-edf292a53db4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28527f9668b9ca6a9ef00cf399a04ce9bad65716
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="recommendations-for-choosing-a-collection-class"></a>コレクション クラスの選択に関する推奨事項
この記事には、特定のアプリケーション ニーズに合わせてコレクション クラスを選択する際に役立つ詳細情報が含まれています。  
  
 コレクション クラスを選択する際は、次の項目を含むさまざまな要素を考慮する必要があります。  
  
-   順序付け、インデックス、パフォーマンスなど、クラス形状の特性。下の表「 [コレクションの形状と特徴](#_core_collection_shape_features) 」を参照してください。  
  
-   クラスで C++ テンプレートを使用しているかどうか  
  
-   コレクションに格納されている要素をシリアル化できるかどうか  
  
-   コレクションに格納されている要素を診断用にダンプできるかどうか  
  
-   タイプ セーフなコレクションかどうか  
  
 次の表「 [コレクションの形状と特徴](#_core_collection_shape_features)」に、使用できるコレクション形状の特性を示します。  
  
-   2 列目と 3 列目は、各形状の順序付けとアクセスに関する特性を示しています。 表に使用されている用語 "順序付け" とは、項目を挿入または削除した順によってコレクション内の項目の位置が決まることを意味します。項目がその内容によって並べ替えられることを意味するのではありません。 用語 "インデックス付き" は、通常の配列内の項目と同様に、コレクション内の項目を整数インデックスによって取得できることを意味します。  
  
-   4 列目と 5 列目は、各形状のパフォーマンスを表しています。 頻繁にコレクションに項目を挿入するアプリケーションでは、項目の挿入速度が特に重要です。他のアプリケーションでは、検索速度の方がより重要になる場合があります。  
  
-   6 列目は、各形状で項目の重複が許可されるかどうかを表しています。  
  
### <a name="_core_collection_shape_features"></a>  コレクションの形状と特徴  
  
|形式|順序あり|インデックスを作成|要素の追加|指定した要素の検索|重複する要素|  
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|  
|リスト|[はい]|×|Fast|遅い|[はい]|  
|配列|[はい]|整数に基づく|遅い|遅い|[はい]|  
|マップ|×|キーに基づく|Fast|Fast|いいえ (キー)、はい (値)|  
  
 次の表「 [MFC コレクション クラスの特性](#_core_characteristics_of_mfc_collection_classes)」に、特定の MFC コレクション クラスの他の重要な特性をまとめてあります。選択の際に参考にしてください。 クラスを選択する際は、通常、クラスが C++ テンプレートをベースにしているかどうか、MFC のドキュメント [シリアル化](../mfc/serialization-in-mfc.md) 機構で要素をシリアル化できるかどうか、MFC の診断ダンプ機構で要素をダンプできるかどうか、クラスがタイプ セーフかどうか (つまり、クラスに基づいてコレクションに格納する項目または取得される項目の型が保証されるかどうか) を考慮します。  
  
### <a name="_core_characteristics_of_mfc_collection_classes"></a>  MFC コレクション クラスの特性  
  
|クラス|C++<br /><br /> テンプレートの使用|シリアル化<br /><br /> できるか|シリアル化<br /><br /> ダンプ|Is<br /><br /> タイプ セーフ|  
|-----------|------------------------------|---------------------------|-----------------------|-----------------------|  
|`CArray`|[はい]|はい 1|はい 1|×|  
|`CByteArray`|Ｘ|はい|[はい]|はい 3|  
|`CDWordArray`|×|はい|[はい]|はい 3|  
|`CList`|[はい]|はい 1|はい 1|×|  
|`CMap`|[はい]|はい 1|はい 1|×|  
|`CMapPtrToPtr`|Ｘ|Ｘ|はい|いいえ|  
|`CMapPtrToWord`|Ｘ|Ｘ|はい|いいえ|  
|`CMapStringToOb`|Ｘ|はい|はい|いいえ|  
|`CMapStringToPtr`|Ｘ|Ｘ|はい|いいえ|  
|`CMapStringToString`|Ｘ|はい|[はい]|はい 3|  
|`CMapWordToOb`|×|はい|はい|いいえ|  
|`CMapWordToPtr`|Ｘ|Ｘ|はい|いいえ|  
|`CObArray`|Ｘ|はい|はい|いいえ|  
|`CObList`|Ｘ|はい|はい|いいえ|  
|`CPtrArray`|Ｘ|Ｘ|はい|いいえ|  
|`CPtrList`|Ｘ|Ｘ|はい|いいえ|  
|`CStringArray`|Ｘ|はい|[はい]|はい 3|  
|`CStringList`|×|はい|[はい]|はい 3|  
|`CTypedPtrArray`|[はい]|状況に依存 2|[はい]|はい|  
|`CTypedPtrList`|[はい]|状況に依存 2|[はい]|はい|  
|`CTypedPtrMap`|[はい]|状況に依存 2|[はい]|はい|  
|`CUIntArray`|いいえ|Ｘ|[はい]|はい 3|  
|`CWordArray`|×|はい|[はい]|はい 3|  
  
 1. をシリアル化を明示的に呼び出す必要があります、コレクション オブジェクトの`Serialize`関数です。 ダンプを明示的に呼び出す必要があります、`Dump`関数。 フォーム `ar << collObj` を使用してシリアル化を行うことはできません。また、フォーム `dmp` `<< collObj` を使用してダンプを行うこともできません。  
  
 2. シリアル化ができるかどうかは、基になるコレクションの型に依存します。 たとえば、型付きポインター配列が `CObArray`に基づいている場合はシリアル化できますが、 `CPtrArray`に基づいている場合はシリアル化できません。 通常、"Ptr" が付くクラスはシリアル化できません。  
  
 3. この列が "はい" の非テンプレート コレクション クラスは、そのクラスの用途どおりに使うとタイプ セーフとなります。 たとえば、 `CByteArray`にバイト データを格納すると、その配列はタイプ セーフです。 しかし、文字データを格納すると、タイプ セーフは保証されません。  
  
## <a name="see-also"></a>関連項目  
 [コレクション](../mfc/collections.md)   
 [テンプレート ベースのクラス](../mfc/template-based-classes.md)   
 [方法: タイプ セーフなコレクションを作成します。](../mfc/how-to-make-a-type-safe-collection.md)   
 [コレクションの全メンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)

