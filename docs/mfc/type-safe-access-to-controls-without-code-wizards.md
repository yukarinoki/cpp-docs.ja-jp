---
title: コード ウィザードを使用しないコントロールへのタイプ セーフ アクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb861995c16411bb58e3051c5ffc78f75931ae8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385766"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>コード ウィザードを使用しない、コントロールへのタイプ セーフ アクセス
コントロールへのタイプ セーフなアクセスを作成するための最初の方法は、クラスの戻り値の型をキャストするインライン メンバー関数を使用して`CWnd`の`GetDlgItem`適切な C++ コントロール型に、この例のように、メンバー関数。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 このメンバー関数を使用して、次のようなコードでタイプ セーフな方法でコントロールにアクセスできます。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [コード ウィザードを使用した、コントロールへのタイプ セーフ アクセス](../mfc/type-safe-access-to-controls-with-code-wizards.md)

