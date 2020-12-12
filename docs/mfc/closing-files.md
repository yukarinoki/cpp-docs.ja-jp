---
description: '詳細情報: ファイルを閉じる'
title: ファイルを閉じる
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: e8d2f0792aeb889c40cb516af259fc2a40890a1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338383"
---
# <a name="closing-files"></a>ファイルを閉じる

通常の i/o 操作では、ファイルの終了後、ファイルを閉じなければなりません。

#### <a name="to-close-a-file"></a>ファイルを閉じるには

1. **Close** メンバー関数を使用します。 この関数は、ファイルシステムファイルを閉じ、必要に応じてバッファーをフラッシュします。

[[ファイルを開く](opening-files.md)] に示されている例のように、フレームに[CFile](reference/cfile-class.md)オブジェクトを割り当てた場合、オブジェクトは自動的に閉じられ、スコープ外に出ると破棄されます。 オブジェクトを削除して `CFile` も、ファイルシステム内の物理ファイルは削除されないことに注意してください。

## <a name="see-also"></a>関連項目

[[ファイル]](files-in-mfc.md)
