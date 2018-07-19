---
title: フレームワークのダイアログ ボックス コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a92846dc1d7b950d1eccfa4cd42b01ac84d96b34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343968"
---
# <a name="dialog-box-components-in-the-framework"></a>フレームワークのダイアログ ボックス コンポーネント
MFC フレームワークでは、ダイアログ ボックスは、2 つのコンポーネントは。  
  
-   ダイアログ ボックスのコントロールとその配置を指定するダイアログ テンプレート リソースです。  
  
     ダイアログ リソースでは、元の Windows がダイアログ ウィンドウを作成し、表示するダイアログ テンプレートを格納します。 テンプレートでは、そのサイズ、場所、スタイル、および型と、ダイアログ ボックスのコントロールの位置を含む、ダイアログ ボックスの特性を指定します。 通常、リソースとして格納されているダイアログ テンプレートを使用するがメモリ内で、独自のテンプレートを作成することもできます。  
  
-   ダイアログ クラスから派生した[CDialog](../mfc/reference/cdialog-class.md)、ダイアログ ボックスを管理するためのプログラム インターフェイスを提供します。  
  
     ダイアログ ボックスでは、ウィンドウは、され、表示されているときに Windows のウィンドウにアタッチされます。 ダイアログ ウィンドウが作成されると、ダイアログ テンプレート リソースは、ウィンドウ コントロール ダイアログ ボックスの子を作成するため、テンプレートとして使用されます。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

