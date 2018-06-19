---
title: ドキュメントの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48f3bd6c6463bbbe26214a29960260d2be583e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385639"
---
# <a name="using-documents"></a>ドキュメントの使い方
連携して、ドキュメントとビュー。  
  
-   含む、管理、およびアプリケーションに固有の表示[データ](../mfc/managing-data-with-document-data-variables.md)です。  
  
-   構成されるインターフェイスを提供[ドキュメント データ変数](../mfc/managing-data-with-document-data-variables.md)データを操作するためです。  
  
-   参加[ファイルの読み書き](../mfc/serializing-data-to-and-from-files.md)です。  
  
-   参加[印刷](../mfc/role-of-the-view-in-printing.md)です。  
  
-   [処理](../mfc/handling-commands-in-the-document.md)ほとんどのアプリケーションのコマンドとメッセージです。  
  
 ドキュメントは、特にデータの管理に関連します。 ドキュメント クラスのメンバー変数に、通常、データを格納します。 ビューでは、これらの変数を使用して、表示用にデータをアクセスし、更新します。 ドキュメントの既定のシリアル化メカニズムでは、ファイルからデータの読み書きを管理します。 ドキュメントは、コマンドを処理できます (Windows ではないメッセージ以外の値が**WM_COMMAND**)。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [CDocument からのドキュメント クラスの派生](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [ドキュメント データ変数を使ったデータを管理](../mfc/managing-data-with-document-data-variables.md)  
  
-   [ファイル間でデータをシリアル化します。](../mfc/serializing-data-to-and-from-files.md)  
  
-   [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [ドキュメント内のコマンドの処理](../mfc/handling-commands-in-the-document.md)  
  
-   [このメンバー関数はでも実質的](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [このメンバー関数は DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)

