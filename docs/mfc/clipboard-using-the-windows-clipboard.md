---
title: 'クリップボード: Windows クリップボードの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed1b3e9cc0cdd368a37657a751df67bed3f72dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342109"
---
# <a name="clipboard-using-the-windows-clipboard"></a>クリップボード : Windows クリップボードの使用方法
このトピックでは、MFC アプリケーション内では、標準の Windows クリップボード API を使用する方法について説明します。  
  
 Windows のほとんどのアプリケーションでは、またはデータを Windows クリップボードにコピーを切り取って、クリップボードからデータをサポートします。 クリップボードのデータ形式は、アプリケーションによって異なります。 フレームワークは、クラスの限られた数の限定された数のクリップボード形式のみをサポートします。 通常、クリップボードに関連するコマンドを実装 — 切り取り、コピー、および貼り付け: ビューの編集 メニュー上。 クラス ライブラリは、これらのコマンドのコマンド Id を定義します。 **ID_EDIT_CUT**、 **ID_EDIT_COPY**、および**ID_EDIT_PASTE**です。 そのメッセージ行プロンプトも定義します。  
  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)メニュー コマンドをハンドラー関数にマップすることによって、アプリケーションでメニュー コマンドを処理する方法について説明します。 アプリケーションでは、[編集] メニュー、クリップボード コマンドに対するハンドラー関数を定義しません、としては無効のままです。 切り取り、コピー コマンドをハンドラー関数を作成するには、アプリケーションでの選択を実装します。 [貼り付け] コマンドをハンドラー関数を記述するには、アプリケーションが受け入れる形式のデータが含まれているかどうかをクリップボードをクエリします。 たとえば、[コピー] コマンドを有効にする可能性がありますハンドラーを記述する、次のような。  
  
 [!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 切り取り、コピー、および貼り付けのコマンドでは、特定のコンテキストで意味のあるのみです。 何かを選択すると、何か場合にのみ、貼り付け コマンドがクリップボードには場合にのみ、切り取り、コピー コマンドを有効にする必要があります。 更新ハンドラー関数を有効または無効に、状況に応じてこれらのコマンドを定義することで、この動作を提供できます。 詳細については、次を参照してください。[ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)です。  
  
 Microsoft Foundation Class ライブラリは、テキストの編集でクリップボードのサポートを提供して、`CEdit`と`CEditView`クラスです。 OLE クラスには、OLE アイテムに関連する実装のクリップボード操作も簡略化します。 OLE クラスの詳細については、次を参照してください。[クリップボード: OLE クリップボード機構を使用して](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)です。  
  
 元に戻すなどのメニュー コマンドを編集するその他の実装 (**ID_EDIT_UNDO**) とやり直し (**ID_EDIT_REDO**)、するものままです。 アプリケーションがこれらのコマンドをサポートしていない場合に簡単に、Visual C リソース エディターを使用して、リソース ファイルから削除することができます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [コピーと貼り付けデータ](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [OLE クリップボード機構の使用](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## <a name="see-also"></a>関連項目  
 [クリップボード](../mfc/clipboard.md)

