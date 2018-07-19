---
title: 標準コマンド id とウィンドウ Id |Microsoft Docs
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
ms.openlocfilehash: 218f0b87edd2ec8c846c08e5cdc72aa01e22c0b1
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886025"
---
# <a name="standard-command-and-window-ids"></a>標準コマンド ID とウィンドウ ID
Microsoft Foundation Class ライブラリでは、afxres.h 内でさまざまな標準のコマンドとウィンドウ Id を定義します。 これらの Id は、メッセージ ハンドラー関数をマッピングするリソース エディターと [プロパティ] ウィンドウ内で最もよく使用されます。 すべての標準コマンドが、 **id _** プレフィックス。 たとえば、メニュー エディターを使用するときに通常にバインドするファイルを開く メニュー項目標準 ID_FILE_OPEN コマンド id。  
  
 標準的なコマンドは、アプリケーション コードする必要はありません、コマンド ID を参照してください、framework 自体がその主な framework クラスのメッセージ マップを通じてコマンドを処理するため、(`CWinThread`、 `CWinApp`、 `CView`、`CDocument`となどの)。  
  
 プレフィックスである標準コマンドの Id だけでなく他の標準的な Id 数が定義されての**AFX_ID**します。 これらの Id は、標準的なウィンドウの Id を含める (プレフィックス**afx_idw _**)、Id の文字列 (プレフィックス**afx_ids _**)、およびその他のいくつかの種類。  
  
 始まる Id、 **AFX_ID**プログラマ、プレフィックスが使用されることはほとんどありませんが、参照することも framework 関数をオーバーライドする場合、これらの Id を参照する必要があります、 **AFX_ID**秒。  
  
 Id がこのリファレンスで個別に記載されていません。 テクニカル ノートの詳細についてを見つけることができます[20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、 [21](../../mfc/tn021-command-and-message-routing.md)、および[22](../../mfc/tn022-standard-commands-implementation.md)します。  
  
> [!NOTE]
>  (.Rc) ファイルは直接 Afxwin.h に含まれます。 次のステートメントは、アプリケーションのリソース スクリプト (.rc) ファイルで明示的に含める必要があります。  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
