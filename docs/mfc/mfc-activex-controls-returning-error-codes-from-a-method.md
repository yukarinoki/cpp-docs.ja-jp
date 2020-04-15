---
title: 'MFC ActiveX コントロール : メソッドからのエラー コードのリターン'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 5314545a3a903158362dbfa65c4a9a1b2143e86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364563"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX コントロール : メソッドからのエラー コードのリターン

この資料では、ActiveX コントロール メソッドからエラー コードを返す方法について説明します。

メソッド内でエラーが発生したことを示すには、パラメーターとして SCODE (状態コード) を受け取る[COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror)メンバー関数を使用する必要があります。 事前定義された SCODE を使用することも、独自の SCODE を定義することもできます。

> [!NOTE]
> `ThrowError`プロパティの Get 関数または Set 関数またはオートメーション メソッド内からエラーを返す手段としてのみ使用されます。 これらは、スタック上に適切な例外ハンドラーが存在する唯一の時間です。

ヘルパー関数は[、COleControl::SetNotSupported、COleControl::GetNotSupported、](../mfc/reference/colecontrol-class.md#setnotsupported)[および COleControl::SetNot許可](../mfc/reference/colecontrol-class.md#setnotpermitted)されたなどの最も一般的な定義済みの SCODEs に対して存在します。 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)

定義済みの SCOD の一覧とカスタム SCOD の定義手順については[、「ActiveX コントロールでの ActiveX コントロールのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md): 詳細トピック」を参照してください。

コードの他の領域での例外の報告の詳細については[、「COleControl::FireError」](../mfc/reference/colecontrol-class.md#fireerror)と「ActiveX コントロールの[ActiveX コントロールでのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md): 詳細トピック」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
