---
title: '方法: テンプレート クラスのメッセージ マップを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6781ca14b174608a815a0300750dd6a3d9aa96bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354781"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>方法 : テンプレート クラスのメッセージ マップを作成する
MFC でのメッセージ マッピングでは、適切な C++ オブジェクトのインスタンスに Windows メッセージを効率的な方法を提供します。 MFC メッセージ マップの対象の例には、アプリケーション クラス、ドキュメントとビュー クラス、コントロール クラス。  
  
 従来の MFC メッセージ マップは、宣言、 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)マクロを各メッセージ ハンドラー クラスのメソッドでのマクロ エントリのメッセージ マップの開始を宣言し、最後に、 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)マクロをメッセージ マップの最後を宣言します。  
  
 1 つの制限と、 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)マクロは、テンプレート引数を含むクラスと組み合わせて使用した場合に発生します。 テンプレート クラスに使用する場合このマクロでは、マクロの展開時にテンプレートのパラメーターが不足しているため、コンパイル時エラーが発生します。 [同じよう](reference/message-map-macros-mfc.md#begin_template_message_map)マクロは、独自のメッセージを宣言する 1 つのテンプレート引数を含むクラスのマップを許可するように設計されました。  
  
## <a name="example"></a>例  
 例について考えて場所 MFC [CListBox](../mfc/reference/clistbox-class.md)クラスの拡張が外部データ ソースとの同期を提供します。 架空**CSyncListBox**クラスに次のように宣言されます。  
  
 [!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]  
  
 **CSyncListBox**クラスは、データ ソースと同期することを説明する 1 つの型で template 宣言されます。 クラスのメッセージ マップに参加する 3 つのメソッドも宣言されています: **OnPaint**、 **OnDestroy**、および**OnSynchronize**です。 **OnSynchronize**メソッドは次のように実装します。  
  
 [!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]  
  
 上記の実装により、 **CSyncListBox**クラスを実装する任意のクラス型に特殊化されて、 **GetCount**メソッドなど**CArray**、 **CList**、および**CMap**です。 **StringizeElement**関数は、テンプレート関数は、次のプロトタイプ宣言されています。  
  
 [!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]  
  
 通常、このクラスのメッセージ マップとして定義されます。  
  
 `BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)`  
  
 `ON_WM_PAINT()`  
  
 `ON_WM_DESTROY()`  
  
 `ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)`  
  
 `END_MESSAGE_MAP()`  
  
 ここで**LBN_SYNCHRONIZE**など、アプリケーションで定義されたカスタム ユーザー メッセージします。  
  
 [!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]  
  
 上記のマクロのマップはコンパイルされず、ためにテンプレートの仕様を**CSyncListBox**クラスはマクロの展開中に失われます。 **同じよう**マクロによって展開されたマクロ マップに指定されたテンプレート パラメーターを組み込むことでこれを解決します。 このクラスのメッセージ マップになります。  
  
 [!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]  
  
 次のサンプルの使用方法を示します、 **CSyncListBox**クラスを使用して、 **CStringList**オブジェクト。  
  
 [!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]  
  
 テストを完了する、 **StringizeElement**関数を使用する特殊化する必要があります、 **CStringList**クラス。  
  
 [!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [同じよう](reference/message-map-macros-mfc.md#begin_template_message_map)   
 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

