---
title: 標準コマンド id とウィンドウ Id |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72b50108a9b880961f0dd8bcded1126a635fb9e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="standard-command-and-window-ids"></a>標準コマンド ID とウィンドウ ID
Microsoft Foundation Class ライブラリでは、afxres.h 内でさまざまな標準のコマンドとウィンドウ Id を定義します。 これらの Id は、メッセージ ハンドラー関数をマッピングするリソース エディターと [プロパティ] ウィンドウ内で最もよく使用されます。 すべての標準コマンドが、 **id _** プレフィックス。 たとえば、メニュー エディターを使用して、通常にバインドするファイルを開くメニュー項目、標準`ID_FILE_OPEN`コマンド ID  
  
 ほとんどの標準のコマンドでは、アプリケーション コードする必要はありませんコマンド ID を参照してください framework 自体はそのプライマリ framework クラスのメッセージ マップを通じてコマンドを処理するため ( `CWinThread`、 `CWinApp`、< c4> `CView` 、 **CDocument**など)。  
  
 標準コマンド Id だけでなく他の標準的な Id の数が定義されて、プレフィックスが付いているの**AFX_ID**です。 これらの Id は、標準的なウィンドウの Id を含める (プレフィックス**afx_idw _**)、Id の文字列 (プレフィックス**afx_ids _**)、およびその他のいくつかの型。  
  
 始まる Id を**AFX_ID**プログラマによってプレフィックスが使用されることはほとんどありませんが、参照も framework 関数をオーバーライドする場合、これらの Id を参照する必要があります、 **AFX_ID**s。  
  
 Id がこのリファレンスで個別に記載されていません。 テクニカル ノートでそれらの詳細についてを見つけることができます[20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、 [21](../../mfc/tn021-command-and-message-routing.md)、および[22](../../mfc/tn022-standard-commands-implementation.md)です。  
  
> [!NOTE]
>  (.Rc) ファイルは直接 Afxwin.h に含まれます。 次のステートメントは、アプリケーションのリソース スクリプト (.rc) ファイルに明示的に含める必要があります。  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
