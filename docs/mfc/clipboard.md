---
title: クリップボード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2ad21bcbff31335f6ec79a4527ef7d99e07e547
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341105"
---
# <a name="clipboard"></a>クリップボードのトピック
この一連のトピックでは、MFC アプリケーションの Windows クリップボードのサポートを実装する方法について説明します。 Windows のクリップボードは、2 つの方法で使用されます。  
  
-   切り取り、コピー、および貼り付けなどの標準的な編集 メニューのコマンドを実装します。  
  
-   実装の統一されたデータはドラッグで転送し、(OLE) を削除します。  
  
 クリップボードは、標準 Windows メソッド、ソースおよび変換先の間でデータを転送するのです。 OLE 操作に便利ことができます。 OLE の出現により、2 つのクリップボード機構にある Windows です。 標準の Windows クリップボード API は、引き続き使用できますが、OLE データ転送メカニズムで補完されたが、します。 OLE 汎用データ転送 (UDT) は、切り取り、コピー、およびクリップボードから貼り付けをサポートし、ドラッグ アンド ドロップします。  
  
 クリップボードとは、Windows セッション全体で共有されるハンドルまたは、独自のクラスがないため、システム サービスです。 クラスのメンバー関数を使用して、クリップボードを管理する[CWnd](../mfc/reference/cwnd-class.md)です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [クリップボード機構を使用する場合](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [従来の Windows クリップボード API を使用します。](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE クリップボード機構の使用](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [コピーと貼り付けデータ](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [その他の形式の追加](../mfc/clipboard-adding-other-formats.md)  
  
-   [Windows のクリップボード](https://msdn.microsoft.com/library/ms648709)  
  
-   [ドラッグ アンド ドロップ (OLE) を実装します。](../mfc/drag-and-drop-ole.md)  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)
