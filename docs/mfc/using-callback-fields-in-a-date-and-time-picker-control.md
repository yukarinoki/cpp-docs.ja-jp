---
title: 日時指定コントロールでのコールバック フィールドの使い方
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 874f73df3dda3a720d4346ae3fb0136c662221db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299401"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>日時指定コントロールでのコールバック フィールドの使い方

日付と時刻の選択フィールドを定義する標準書式指定文字、だけでなく、コールバック フィールドとしてカスタム書式指定文字列の特定の部分を指定することで、出力をカスタマイズできます。 コールバック フィールドを宣言するには、1 つまたは複数の"X"文字 (ASCII コード 88) を書式設定文字列の本文に任意の場所含めます。 たとえば、次の文字列"' は現在: 'yy '/' MM '/' dd' (1 日 'X')'"原因として、年、月、日、および最後に、年の通算日後に、現在の値を表示する日付と時刻の選択コントロールです。

> [!NOTE]
>  数 X コールバックでは、フィールドは表示される文字数に対応しません。

"X"文字を繰り返すことにより、カスタムの文字列で複数のコールバック フィールドを区別することができます。 そのため、書式設定文字列"XXddddMMMdd'、' yyyXXX"、"XX"と"XXX"の 2 つの一意のコールバック フィールドが含まれています。

> [!NOTE]
>  コールバック フィールドは、DTN_WMKEYDOWN 通知メッセージを処理するために、アプリケーションを準備する必要がありますので、有効なフィールドとして扱われます。

日付と時刻の選択コントロールでのコールバック フィールドの実装は、3 つの部分で構成されます。

- カスタム書式指定文字列を初期化しています

- DTN_FORMATQUERY 通知の処理

- DTN_FORMAT 通知の処理

## <a name="initializing-the-custom-format-string"></a>カスタム書式指定文字列を初期化しています

呼び出してカスタム文字列を初期化`CDateTimeCtrl::SetFormat`します。 詳細については、次を参照してください。[日付と時刻の選択コントロールでカスタム書式指定文字列を使用して](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)します。 カスタム書式指定文字列を設定する一般的な場所は、`OnInitDialog`含むダイアログ クラスの関数または`OnInitialUpdate`親ビュー クラスの関数。

## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY 通知の処理

コントロールは、書式指定文字列を解析し、コールバック フィールドを検出すると、アプリケーションは DTN_FORMAT と DTN_FORMATQUERY 通知メッセージを送信します。 コールバック フィールドの文字列は、照会されるコールバック フィールドを特定できるように、通知に含まれています。

DTN_FORMATQUERY 通知を送信して、現在のコールバック フィールドに表示される文字列のピクセル単位の最大許容サイズを取得します。

この値を正しく計算するには、必要がありますを計算する、フィールドの代わりに使用する、文字列の幅と高さコントロールの表示フォントを使用します。 呼び出して、文字列の実際の計算を簡単に行う、 [GetTextExtentPoint32](/windows/desktop/api/wingdi/nf-wingdi-gettextextentpoint32a) Win32 関数。 サイズが決まったら、値をアプリケーションに渡すし、ハンドラー関数を終了します。

次の例では、コールバック文字列のサイズを指定する 1 つの方法を示します。

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

現在のコールバック フィールドのサイズが計算された後は、フィールドの値を指定してください。 これは、DTN_FORMAT 通知のハンドラーで行います。

## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT 通知の処理

DTN_FORMAT 通知は、置換される文字の文字列を要求するアプリケーションによって使用されます。 次の例では、1 つの可能なメソッドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  ポインター、 **NMDATETIMEFORMAT**構造が適切な型に通知ハンドラーの最初のパラメーターをキャストすることによって検出されました。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
