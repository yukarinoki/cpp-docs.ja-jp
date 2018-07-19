---
title: テンプレートの作成を文書化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC]
- constructors [MFC], document template
- document templates [MFC], creating
- MFC, document templates
- templates [MFC], document templates
ms.assetid: c87f1821-7cbf-442e-9690-f126ae7fb783
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3695d2795fa324051b76cf012aae7e1b1f275fa1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928023"
---
# <a name="document-template-creation"></a>ドキュメント テンプレートの作成
応答で、新しいドキュメントを作成するときに、**新規**または**開く**コマンドを**ファイル**] メニューの [ドキュメント テンプレートもウィンドウを作成新しいフレームを表示するため、ドキュメントです。  
  
 ドキュメント テンプレートのコンス トラクターは、ドキュメント、windows、およびビューを作成できるテンプレートの種類を指定します。 これは、ドキュメント テンプレートのコンス トラクターに渡す引数によって決まります。 次のコード例の作成、 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)サンプル アプリケーションについては。  
  
 [!code-cpp[NVC_MFCDocView#7](../mfc/codesnippet/cpp/document-template-creation_1.cpp)]  
  
 新しいポインター`CMultiDocTemplate`オブジェクトに渡す引数として使用[AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate)です。 引数、`CMultiDocTemplate`コンス トラクターは、ドキュメントの種類のメニューとアクセラレータに関連付けられているリソース ID を含めるしの 3 つを使用して、 [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class)マクロです。 `RUNTIME_CLASS` 返します、 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)引数としてという名前の C++ クラスのオブジェクト。 3 つ`CRuntimeClass`ドキュメント テンプレートのコンス トラクターに渡されたオブジェクトは、ドキュメントの作成プロセス中に、指定されたクラスの新しいオブジェクトを作成するために必要な情報を指定します。 作成するドキュメント テンプレートの作成の例、`CScribDoc`オブジェクトと`CScribView`接続されているオブジェクト。 ビューは、標準の MDI 子フレーム ウィンドウで囲まれます。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

