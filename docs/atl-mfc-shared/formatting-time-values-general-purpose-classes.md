---
title: 時刻の値を書式設定。汎用クラス
ms.date: 11/04/2016
helpviewer_keywords:
- dates, calculating intervals
- elapsed time, string representation
- time [C++], formatting
- formatting [C++], time
ms.assetid: 7fcfee24-f874-4a4d-95b3-adc19a0f2df0
ms.openlocfilehash: bab93638d81e8e4e5d6f7ce71bf6a3180fa7f7e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236401"
---
# <a name="formatting-time-values-general-purpose-classes"></a>時刻の値を書式設定。汎用クラス

次の手順では、時間の値の書式設定する方法を示します。

#### <a name="to-format-a-string-representation-of-a-time-or-elapsed-time"></a>時間の経過時間の文字列形式の書式設定

使用して、`Format`からいずれかのメンバー関数、 [CTime](../atl-mfc-shared/reference/ctime-class.md)または[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)文字を作成するクラスは次の例に示すように、時間の経過時間の表現を文字列します。

   [!code-cpp[NVC_ATLMFC_Utilities#175](../atl-mfc-shared/codesnippet/cpp/formatting-time-values-general-purpose-classes_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [MFC の一般的な日付と時刻](../atl-mfc-shared/date-and-time.md)

- [SYSTEMTIME の操作](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [日付と時刻のオートメーションのサポート](../atl-mfc-shared/date-and-time-automation-support.md)
