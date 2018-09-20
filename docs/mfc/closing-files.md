---
title: ファイルを閉じる |Microsoft Docs
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
ms.openlocfilehash: 9c392ef728e1d796a02cfa32edc2c3e8c74d083b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426238"
---
# <a name="closing-files"></a>ファイルを閉じる

通常どおり、I/O 操作でファイルを終了すると閉じてください。

#### <a name="to-close-a-file"></a>ファイルを閉じる

1. 使用して、**閉じる**メンバー関数。 この関数は、ファイル システムのファイルを閉じ、必要な場合は、バッファーをフラッシュします。

割り当て済みの場合、 [CFile](../mfc/reference/cfile-class.md)フレーム上のオブジェクト (に示す例のように[ファイルを開く](../mfc/opening-files.md))、オブジェクトが自動的に閉じてスコープ外になったときに破棄されます。 削除することに注意してください、`CFile`オブジェクトには、ファイル システムで物理ファイルは削除されません。

## <a name="see-also"></a>関連項目

[ファイル](../mfc/files-in-mfc.md)

