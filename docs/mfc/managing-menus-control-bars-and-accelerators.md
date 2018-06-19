---
title: メニューのコントロール バー、およびアクセラレータの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1055fd9b1ef75b2090478d85e8251d1800b8b039
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345743"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>メニュー、コントロール バー、およびアクセラレータの管理
フレーム ウィンドウは、メニューのツールバー、ステータス バー、およびアクセラレータを含め、更新のユーザー インターフェイス オブジェクトを管理します。 また、MDI アプリケーションでメニュー バーの共有を管理します。  
  
## <a name="managing-menus"></a>メニューの管理  
 使用してユーザー インターフェイス項目を更新中に参加するフレーム ウィンドウ、`ON_UPDATE_COMMAND_UI`メカニズムで説明されて[ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)です。 ツールバーとその他のコントロール バーのボタンは、アイドル ループ時に更新されます。 ドロップダウン メニューの直前に、メニュー バーでのドロップダウン メニューにメニュー項目が更新されます。  
  
 MDI アプリケーションでは、MDI フレーム ウィンドウは、メニュー バーとキャプションを管理します。 MDI フレーム ウィンドウには、アクティブな MDI 子ウィンドウがない場合に、メニュー バーとして使用する 1 つの既定のメニューが所有しています。 アクティブな子が存在する場合、その MDI フレーム ウィンドウのメニュー バーと、アクティブな MDI 子ウィンドウのメニューが引き継がれます。 MDI アプリケーションは、グラフとワークシートのドキュメントなど、複数のドキュメント タイプをサポートしている場合、各型は、メニュー バーに独自のメニューを配置して、メイン フレーム ウィンドウのキャプションを変更します。  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI アプリケーションで、[ウィンドウ] メニューに表示される標準のコマンドの既定の実装を提供します。 特に、新しいウィンドウのコマンド (**ID_WINDOW_NEW**) は、新しいフレーム ウィンドウと現在のドキュメントのビューを作成する実装します。 高度なカスタマイズが必要な場合にのみ、これらの実装をオーバーライドする必要があります。  
  
 ドキュメントの種類が同一の複数の MDI 子ウィンドウは、メニュー リソースを共有します。 場合同じのドキュメント テンプレートでは、いくつかの MDI 子ウィンドウが作成された、すべて使用できます同じメニュー リソースに対して Windows のシステム リソースを保存します。  
  
## <a name="managing-the-status-bar"></a>ステータス バーの管理  
 フレーム ウィンドウも、クライアント領域内のステータス バーを配置し、状態を管理するバーのインジケーター。 フレーム ウィンドウをクリアし、必要に応じて、ステータス バーにメッセージ領域を更新し、」の説明に従って、ユーザーがメニュー項目またはツール バー ボタンを選択すると表示文字列を表示[ステータス バーにコマンド情報を表示する方法](../mfc/how-to-display-command-information-in-the-status-bar.md)です。  
  
## <a name="managing-accelerators"></a>アクセラレータの管理  
 各フレーム ウィンドウは、自動的に変換するためにアクセラレータ キーボードを省略可能なアクセラレータ テーブルを保持します。 このメカニズムでは、簡単にメニュー コマンドを実行するアクセス キー (ショートカット キーとも呼ばれます) を定義します。  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

