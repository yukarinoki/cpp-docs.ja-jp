---
title: モードレス ダイアログ ボックスの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2055312c7418b14c9b274649db8faa297554257e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="creating-modeless-dialog-boxes"></a>モードレス ダイアログ ボックスの作成
モードレス ダイアログ ボックスのダイアログ クラスに、独自のパブリック コンス トラクターを提供する必要があります。 モードレス ダイアログ ボックスを作成する、パブリック コンス トラクターを呼び出すし、ダイアログ オブジェクトを呼び出す[作成](../mfc/reference/cdialog-class.md#create)ダイアログ リソースを読み込むためのメンバー関数。 呼び出すことができます**作成**中またはコンス トラクターの呼び出し後です。 ダイアログ リソースに、プロパティが設定されている場合**WS_VISIBLE**、ダイアログ ボックスがすぐに表示されます。 場合は、呼び出す必要があります、 [ShowWindow](../mfc/reference/cwnd-class.md#showwindow)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

