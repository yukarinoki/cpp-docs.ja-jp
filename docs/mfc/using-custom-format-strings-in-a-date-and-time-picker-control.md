---
description: '詳細情報: 日付と時刻の選択コントロールでのカスタム書式指定文字列の使用'
title: 日時指定コントロールでのカスタム書式指定文字列の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 91add199ffd852a107588617d47a2fd51136596d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154553"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>日時指定コントロールでのカスタム書式指定文字列の使い方

既定では、日付と時刻の選択コントロールには、現在の日付または時刻を表示するための3つの書式の種類 (一意のスタイルに対応する各形式) が用意されています。

- **DTS_LONGDATEFORMAT** 日付を長い形式で表示し、"水曜日, January 3, 2000" のような出力を生成します。

- **DTS_SHORTDATEFORMAT** 日付を短い形式で表示し、"1/3/00" のような出力を生成します。

- **DTS_TIMEFORMAT** 長い形式で時刻を表示し、"5:31:42 PM" のような出力を生成します。

ただし、カスタム書式指定文字列を使用して、日付または時刻の外観をカスタマイズできます。 このカスタム文字列は、既存のフォーマット文字、非形式文字、またはその両方の組み合わせで構成されます。 カスタム文字列が構築されたら、カスタム文字列を渡して [cdatetimectrl 使い方:: SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) を呼び出します。 日付と時刻の選択コントロールには、カスタム書式指定文字列を使用して現在の値が表示されます。

次のコード例 ( *m_dtPicker* は `CDateTimeCtrl` オブジェクト) は、考えられる1つの解決策を示しています。

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

カスタム書式指定文字列に加えて、日付と時刻の選択コントロールでも [コールバックフィールド](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)がサポートされます。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
