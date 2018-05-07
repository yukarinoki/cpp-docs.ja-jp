---
title: 文書化し、MFC アプリケーション ウィザードで作成したクラスの表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b83886784970492da0c5e2a335dbe08119ecaae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC のアプリケーション ウィザードで作成されるドキュメント クラスとビュー クラス
MFC アプリケーション ウィザードできますを簡単に開始プログラムの開発をスケルトンのドキュメントとビュー クラスを作成することで。 できます[コマンドとメッセージをこれらのクラスにマップ](../mfc/reference/mapping-messages-to-functions.md)およびそのメンバー関数を作成する Visual C ソース コード エディターを使用します。  
  
 MFC アプリケーション ウィザードによって作成されたドキュメント クラスがクラスから派生した[CDocument](../mfc/reference/cdocument-class.md)です。 ビュー クラスから派生[CView](../mfc/reference/cview-class.md)です。 アプリケーション ウィザード ダイアログ ボックスで指定すること、アプリケーションのウィザードは、これらのクラスとプロジェクト名に基づいてこれらを含むファイルの名前。 アプリケーション ウィザードで、既定の名前を変更するのにクラスの生成 ページを使用できます。  
  
 一部のアプリケーションには、1 つ以上のドキュメント クラス、ビュー クラス、またはフレーム ウィンドウ クラスを必要があります。 詳細については、次を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)します。  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

