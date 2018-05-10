---
title: 日付と時刻の選択でカスタム書式指定文字列を使用してコントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2b365439f1681cf72bd58218ea4f55fbb2f44c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>日時指定コントロールでのカスタム書式指定文字列の使い方
既定では、日付と時刻の選択コントロールは、現在の日付または時刻を表示するための種類 (形式は一意のスタイルに対応する各) を書式設定 3 つ提供します。  
  
-   **DTS_LONGDATEFORMAT** 「水曜日、2000 年 1 月 3日」のように、長い書式の日付を表示します。  
  
-   **DTS_SHORTDATEFORMAT** 「1/3/00」ように、短い書式の日付を表示します。  
  
-   **DTS_TIMEFORMAT** "5時 31分: 42 PM"のような出力を生成する、長い形式の時刻が表示されます。  
  
 ただし、カスタム書式指定文字列を使用して、日付または時刻の外観をカスタマイズできます。 このカスタムの文字列で構成された既存の書式指定文字、非書式指定文字、または両方の組み合わせのいずれか。 カスタム文字列が作成されると、呼び出しを行う[CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat)カスタムの文字列を渡します。 日付と時刻の選択コントロールは、次に、カスタム書式指定文字列を使用して現在の値が表示されます。  
  
 次のコード例 (ここで`m_dtPicker`は、`CDateTimeCtrl`オブジェクト) 1 つの考えられる解決方法を示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 カスタム書式指定文字列だけでなく制御もサポートに日付と時刻のピッカー[コールバック フィールド](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

