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
ms.openlocfilehash: 425cbf2f9c769dbbb6cd054b9af6b7f6f5fc9d52
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954466"
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
  
2.  次に示すように、クラス宣言 DECLARE_DYNAMIC マクロを使用します。  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]  
  
3.  IMPLEMENT_DYNAMIC マクロを使用して、実装ファイル内 (です。CPP) クラス。 このマクロを引数として受け取り、クラスとその基本クラスの名前として次のようにします。  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  実装ファイルに IMPLEMENT_DYNAMIC を常に配置 (です。CPP) クラス。 IMPLEMENT_DYNAMIC マクロは、コンパイル時に 1 回だけ評価される必要があり、そのため、インターフェイス ファイルでは使用できません (です。複数のファイルに H) を含めること可能性があります。  
  
#### <a name="_core_to_add_dynamic_creation_support"></a> 動的な作成のサポートを追加するには  
  
1.  クラスを派生`CObject`です。  
  
2.  クラス宣言で DECLARE_DYNCREATE マクロを使用します。  
  
3.  (既定のコンス トラクター) を引数なしのコンス トラクターを定義します。  
  
4.  クラスの実装ファイルには、IMPLEMENT_DYNCREATE マクロを使用します。  
  
#### <a name="_core_to_add_serialization_support"></a> シリアル化のサポートを追加するには  
  
1.  クラスを派生`CObject`です。  
  
2.  上書き、`Serialize`メンバー関数。  
  
    > [!NOTE]
    >  呼び出す場合`Serialize`直接、つまり、たくないポリモーフィックなポインターを通じてオブジェクトをシリアル化するには、手順 3. ~ 5. を省略します。  
  
3.  DECLARE_SERIAL マクロを使用して、クラス宣言にします。  
  
4.  (既定のコンス トラクター) を引数なしのコンス トラクターを定義します。  
  
5.  IMPLEMENT_SERIAL マクロを使用して、クラス ファイルに実装します。  
  
> [!NOTE]
>  「ポリモーフィックなポインター」クラスのオブジェクトを指します (それを呼び出す A)、(たとえば、B) から派生したクラスのオブジェクトにします。 ポリモーフィックなポインターを使ってシリアル化するには、フレームワークはいくつかの基本クラス (A) から派生したクラスのオブジェクトであるために、(B) をシリアル化されたオブジェクトのランタイム クラスを決定する必要があります。  
  
 クラスを派生させる場合は、シリアル化を有効にする方法の詳細については`CObject`、記事を参照して[MFC のファイル](../mfc/files-in-mfc.md)と[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject からのクラスの派生](../mfc/deriving-a-class-from-cobject.md)
