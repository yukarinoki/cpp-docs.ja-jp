---
title: ファイルを閉じる
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 04e5084615b1f1cf85d9f41e2c4dcc84910b9d05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636264"
---
# <a name="closing-files"></a>ファイルを閉じる

通常どおり、I/O 操作でファイルを終了すると閉じてください。

#### <a name="to-close-a-file"></a>ファイルを閉じる

1. 使用して、**閉じる**メンバー関数。 この関数は、ファイル システムのファイルを閉じ、必要な場合は、バッファーをフラッシュします。

割り当て済みの場合、 [CFile](../mfc/reference/cfile-class.md)フレーム上のオブジェクト (に示す例のように[ファイルを開く](../mfc/opening-files.md))、オブジェクトが自動的に閉じてスコープ外になったときに破棄されます。 削除することに注意してください、`CFile`オブジェクトには、ファイル システムで物理ファイルは削除されません。

## <a name="see-also"></a>関連項目

[ファイル](../mfc/files-in-mfc.md)

