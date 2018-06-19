---
title: ファイルを閉じる |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97bd910ae4cb514cda07dd319f37a05a32712909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341027"
---
# <a name="closing-files"></a>ファイルを閉じる
通常どおり I/O 操作で、ファイルを終了すると、閉じてください。  
  
#### <a name="to-close-a-file"></a>ファイルを閉じる  
  
1.  使用して、**閉じる**メンバー関数。 この関数は、ファイル システム ファイルを閉じ、必要な場合は、バッファーをフラッシュします。  
  
 割り当てた場合、 [CFile](../mfc/reference/cfile-class.md)フレーム上のオブジェクト (に示す例のように[ファイルを開く](../mfc/opening-files.md))、オブジェクトが自動的に終了して、スコープ外になったときに破棄されるあります。 削除することに注意してください、`CFile`オブジェクトには、ファイル システムで物理ファイルは削除されません。  
  
## <a name="see-also"></a>関連項目  
 [ファイル](../mfc/files-in-mfc.md)

