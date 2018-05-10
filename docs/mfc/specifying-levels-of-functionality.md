---
title: 機能レベルを指定する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f32b9502d2e8bd1c1483d817b759ca204f5c9c1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-levels-of-functionality"></a>継承機能のレベルの指定
この記事は、次の機能レベルに追加する方法を説明します、 [CObject](../mfc/reference/cobject-class.md)-派生クラス。  
  
-   [ランタイム クラス情報](#_core_to_add_run.2d.time_class_information)  
  
-   [動的生成機能のサポート](#_core_to_add_dynamic_creation_support)  
  
-   [シリアル化のサポート](#_core_to_add_serialization_support)  
  
 全般の詳細については`CObject`機能、記事を参照して[CObject からクラスを派生する](../mfc/deriving-a-class-from-cobject.md)です。  
  
-   [ランタイム クラス情報](#_core_to_add_run.2d.time_class_information)  
#### <a name="_core_to_add_run.2d.time_class_information"></a> ランタイム クラス情報を追加するには  
  
1.  クラスを派生`CObject`で説明されている、 [CObject からクラスを派生する](../mfc/deriving-a-class-from-cobject.md)資料です。  
  
2.  使用して、`DECLARE_DYNAMIC`マクロは、ここに示すように、クラス宣言で。  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  使用して、`IMPLEMENT_DYNAMIC`実装ファイル内のマクロ (です。CPP) クラス。 このマクロを引数として受け取り、クラスとその基本クラスの名前として次のようにします。  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  常に put`IMPLEMENT_DYNAMIC`実装ファイル (です。CPP) クラス。 `IMPLEMENT_DYNAMIC`マクロは、コンパイル時に 1 回だけ評価される必要があり、そのため、インターフェイス ファイルでは使用できません (です。複数のファイルに H) を含めること可能性があります。  
  
#### <a name="_core_to_add_dynamic_creation_support"></a> 動的な作成のサポートを追加するには  
  
1.  クラスを派生`CObject`です。  
  
2.  使用して、`DECLARE_DYNCREATE`クラス宣言内のマクロです。  
  
3.  (既定のコンス トラクター) を引数なしのコンス トラクターを定義します。  
  
4.  使用して、`IMPLEMENT_DYNCREATE`クラス実装ファイル内のマクロです。  
  
#### <a name="_core_to_add_serialization_support"></a> シリアル化のサポートを追加するには  
  
1.  クラスを派生`CObject`です。  
  
2.  上書き、`Serialize`メンバー関数。  
  
    > [!NOTE]
    >  呼び出す場合`Serialize`直接、つまり、たくないポリモーフィックなポインターを通じてオブジェクトをシリアル化するには、手順 3. ~ 5. を省略します。  
  
3.  使用して、`DECLARE_SERIAL`クラス宣言内のマクロです。  
  
4.  (既定のコンス トラクター) を引数なしのコンス トラクターを定義します。  
  
5.  使用して、`IMPLEMENT_SERIAL`クラス実装ファイル内のマクロです。  
  
> [!NOTE]
>  「ポリモーフィックなポインター」クラスのオブジェクトを指します (それを呼び出す A)、(たとえば、B) から派生したクラスのオブジェクトにします。 ポリモーフィックなポインターを使ってシリアル化するには、フレームワークはいくつかの基本クラス (A) から派生したクラスのオブジェクトであるために、(B) をシリアル化されたオブジェクトのランタイム クラスを決定する必要があります。  
  
 クラスを派生させる場合は、シリアル化を有効にする方法の詳細については`CObject`、記事を参照して[MFC のファイル](../mfc/files-in-mfc.md)と[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject からのクラスの派生](../mfc/deriving-a-class-from-cobject.md)
