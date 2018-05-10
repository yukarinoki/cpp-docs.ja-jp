---
title: ファイルの状態 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d424502e991ea355a6e31bba8fedccb6d5ad2fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-file-status"></a>ファイルの状態の操作
`CFile` サポートしているファイルの状態のファイルが存在するかどうかなど、作成と変更の日付と時間、論理サイズ、およびパスを取得します。  
  
### <a name="to-get-file-status"></a>ファイルの状態を取得するには  
  
1.  使用して、 [CFile](../mfc/reference/cfile-class.md)クラスを取得し、ファイルに関する情報を設定します。 1 つの便利なアプリケーションは、使用する、`CFile`静的メンバー関数**GetStatus**ファイルが存在するかどうかを確認します。 **GetStatus**指定したファイルが存在しない場合は 0 を返します。  
  
 結果を使用するため、 **GetStatus**を使用するかどうかを決定する、 **CFile::modeCreate**次の例に示すように、ファイルを開くときにフラグを設定します。  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 関連情報については、次を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ファイル](../mfc/files-in-mfc.md)

