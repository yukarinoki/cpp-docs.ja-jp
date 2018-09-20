---
title: ファイルの状態 |Microsoft Docs
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
ms.openlocfilehash: 9f7c2d5d76616ed78768b5e133029cf047ed4453
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416819"
---
# <a name="accessing-file-status"></a>ファイルの状態の操作

`CFile` ファイルが存在するかどうかなど、ファイルの状態、作成と変更の日付と時間、論理サイズ、およびパスの取得をサポートします。

### <a name="to-get-file-status"></a>ファイルの状態を取得するには

1. 使用して、 [CFile](../mfc/reference/cfile-class.md)クラスを取得し、ファイルに関する情報を設定します。 1 つの便利なアプリケーションは、使用する、`CFile`静的メンバー関数**GetStatus**ファイルが存在するかどうかを判断します。 **GetStatus**指定したファイルが存在しない場合は 0 を返します。

結果を使用するために、 **GetStatus**を使用するかどうかを判断する、 **CFile::modeCreate**次の例に示すように、ファイルを開くときにフラグを設定します。

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

関連情報については、次を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)します。

## <a name="see-also"></a>関連項目

[ファイル](../mfc/files-in-mfc.md)

