---
title: ドラッグ アンド ドロップ (OLE) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc23c7695bf5afa22734c382ddc72e8418ff74c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344338"
---
# <a name="drag-and-drop-ole"></a>ドラッグ アンド ドロップ (OLE)
OLE のドラッグ アンド ドロップ機能は、主にコピーし、データの貼り付けのショートカットです。 クリップボードにコピーまたはデータの貼り付けを使用する場合は、いくつかの手順が必要です。 データを選択し、をクリックする**切り取り**または**コピー**から、**編集** メニューの コピー先ファイル、ウィンドウまたはアプリケーションに移動カーソルを置き、目的の場所と をクリックします**貼り付け**から、**編集**メニュー。  
  
 OLE のドラッグ アンド ドロップとは異なりますファイル マネージャー ドラッグ アンド ドロップ メカニズム、ファイル名のみを処理し、具体的にはファイル名をアプリケーションに渡すよう設計されています。 OLE のドラッグ アンド ドロップより一般的です。 ドラッグ アンド ドロップのデータをクリップボードにも配置することができます。  
  
 OLE のドラッグ アンド ドロップを使用する場合は、プロセスから 2 つの手順を削除します。 目的の宛先 (「ドロップ ターゲット上の」) にドラッグ、およびマウス ボタンを離すドロップのデータ ソース ウィンドウ (「ドロップ ソース」) を選択します。 操作を使用して、メニューの必要はなくなり、コピー/貼り付けの順序よりも高速です。 唯一の要件は、ドロップ ソースとドロップ ターゲットの両方でなければならないこと開かれていて、少なくとも、画面に部分的に表示します。  
  
 OLE のドラッグ アンド ドロップを使用して、データ間で転送できる 1 つの場所またはアプリケーション間で異なるドキュメント間で、ドキュメント内の別にします。 コンテナーまたはサーバー アプリケーションのいずれかで実装することし、すべてのアプリケーションは、ドロップ ソース、ドロップ ターゲット、またはその両方を指定できます。 アプリケーションに実装されているドロップ ソースとドロップ ターゲットの両方のサポートがある場合は、ドラッグ アンド ドロップが有効になっている子ウィンドウ間または 1 つのウィンドウ内で。 この機能にできる、アプリケーションがずっと使いやすくください。  
  
 OLE のドラッグ アンド ドロップ機能を使用する場合は、「[ドラッグ アンド ドロップ: カスタマイズ](../mfc/drag-and-drop-customizing.md)です。 その記事で説明した手法を使用すると、非 OLE アプリケーションのソースを削除することです。 アーティクル[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)OLE と非 OLE アプリケーションの両方のドロップ ターゲットのサポートを実装する方法について説明します。 これも役に立つ、MFC OLE サンプルを調べて[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)です。  
  
 まだ読んでいない場合、[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)ファミリの記事は、これを行うようになりましたする可能性があります。 これらの記事では、データ転送、およびアプリケーションに実装する方法の基礎について説明します。  
  
 ドラッグ アンド ドロップする方法の詳細については、次を参照してください。  
  
-   [ドラッグ アンド ドロップ: ドロップ ソースの実装](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [ドラッグ アンド ドロップ: カスタマイズ](../mfc/drag-and-drop-customizing.md)  
  
## <a name="see-also"></a>関連項目  
 [OLE](../mfc/ole-in-mfc.md)   
 [データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)

