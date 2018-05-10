---
title: 'TN070: MFC のウィンドウ クラス名 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.classes
dev_langs:
- C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c66c434503bbd2c6d7ee1b0557fa73d843e0caaa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn070-mfc-window-class-names"></a>テクニカル ノート 70: MFC のウィンドウ クラス名
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 MFC のウィンドウでは、ウィンドウの機能を反映する動的に作成されたクラス名を使用します。 MFC では、クラス名のフレーム ウィンドウ、ビュー、およびアプリケーションによって生成されたポップアップ ウィンドウを動的に生成されます。 ダイアログ ボックスとコントロールの MFC アプリケーションによって生成される対象のウィンドウのクラスの Windows が指定した名前であります。  
  
 独自のウィンドウ クラスを登録してのオーバーライドでの使用によって動的に指定されたクラス名を置き換えることができます[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)です。 MFC が指定したクラス名に合わせて次の 2 つのフォームのいずれか。  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 置換される 16 進数字、`%x`からのデータの文字が入力、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体。 MFC は、この手法を使用できるように同一を必要とする複数の C++ クラス**WNDCLASS**構造体は、同じ登録ウィンドウ クラスを共有できます。 ほとんどの単純な Win32 アプリケーションとは異なり MFC アプリケーションがある 1 つだけ**WNDPROC**簡単に共有できるように、 **WNDCLASS**時間とメモリを節約する構造体。 値に置き換え、`%x`文字の前に示したとおりです。  
  
- **WNDCLASS.hInstance**  
  
- **WNDCLASS.style**  
  
- **WNDCLASS.hCursor**  
  
- **WNDCLASS.hbrBackground**  
  
- **WNDCLASS.hIcon**  
  
 最初のフォーム (`Afx:%x:%x`) ときに使用される**hCursor**、 **hbrBackground**、および**hIcon**すべて**NULL**です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)   
 [テクニカル ノート 20: ID 名および番号に関する規約](../mfc/tn020-id-naming-and-numbering-conventions.md)

