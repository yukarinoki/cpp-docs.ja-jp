---
title: 日付と時間 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9753578de006ed46719d94d5861035ab77dbca6c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752253"
---
# <a name="date-and-time"></a>日付と時刻

MFC には、日付と時刻を使用した作業のいくつかの方法がサポートされています。 次の設定があります。

- 汎用の時刻のクラス。 [CTime](../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)クラスのほとんどの時間で宣言されている ANSI 標準ランタイム ライブラリに関連付けられている機能をカプセル化します。H.

- システム クロックをサポートします。 追加されたサポート mfc バージョン 3.0、 `CTime` win32`SYSTEMTIME`と`FILETIME`データ型。

- オートメーションのサポート[DATE データ型](../atl-mfc-shared/date-type.md)します。 サポートの日付、時刻、および日付/時刻値。 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)と[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)クラスは、この機能をカプセル化します。 動作する、 [COleVariant](../mfc/reference/colevariant-class.md)クラスのオートメーションのサポートを使用します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [日付と時刻: SYSTEMTIME サポート](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [日付と時刻: オートメーション サポート](../atl-mfc-shared/date-and-time-automation-support.md)

- [日付と時刻: データベース サポート](../atl-mfc-shared/date-and-time-database-support.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)   
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)

