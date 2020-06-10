---
title: ファイルの状態の操作
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 23c626940e700d3e9827ef6a7cf849d970e40d5d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619784"
---
# <a name="accessing-file-status"></a>ファイルの状態の操作

`CFile`では、ファイルが存在するかどうか、日付と時刻の作成と変更、論理サイズ、パスなど、ファイルの状態の取得もサポートされています。

### <a name="to-get-file-status"></a>ファイルの状態を取得するには

1. ファイルに関する情報を取得および設定するには、 [CFile](reference/cfile-class.md)クラスを使用します。 1つの便利なアプリケーションは、 `CFile` 静的メンバー関数**GetStatus**を使用して、ファイルが存在するかどうかを判断することです。 指定されたファイルが存在しない場合、 **GetStatus**は0を返します。

このため、 **GetStatus**の結果を使用して、次の例に示すように、ファイルを開くときに**CFile:: modeCreate**フラグを使用するかどうかを決定できます。

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

関連情報については、「[シリアル化](serialization-in-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[[ファイル]](files-in-mfc.md)
