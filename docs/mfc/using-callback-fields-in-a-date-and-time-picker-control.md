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
ms.openlocfilehash: 50350e51b6747d8c010db9d0dcaa9dff2e56e1f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366557"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>日時指定コントロールでのコールバック フィールドの使い方

日付と時刻の選択フィールドを定義する標準の書式指定文字に加えて、カスタム書式指定文字列の特定の部分をコールバック フィールドとして指定することで、出力をカスタマイズできます。 コールバック フィールドを宣言するには、書式指定文字列の本体の任意の場所に 1 つ以上の "X" 文字 (ASCII Code 88) を含めます。 たとえば、次の文字列 "'Today は'yy'/'MM'/'dd' (日 'X')' の場合、日付と時刻の選択コントロールは、年の後に月、日付、そして最後に年の日が続く現在の値を表示します。

> [!NOTE]
> コールバック フィールド内の X の数が、表示される文字数と一致しません。

カスタム文字列内の複数のコールバック フィールドを区別するには、"X" 文字を繰り返します。 したがって、書式文字列 "XXxdddMMMdd'、'yyyXXX" には、"XX" と "XXX" という 2 つの一意のコールバック フィールドが含まれています。

> [!NOTE]
> コールバック フィールドは有効なフィールドとして扱われるので、アプリケーションはDTN_WMKEYDOWN通知メッセージを処理できるように準備する必要があります。

日付と時刻の選択コントロールでコールバック フィールドを実装する 3 つの部分で構成されます。

- カスタム書式指定文字列の初期化

- DTN_FORMATQUERY通知の処理

- DTN_FORMAT通知の処理

## <a name="initializing-the-custom-format-string"></a>カスタム書式指定文字列の初期化

への呼び出しを使用して`CDateTimeCtrl::SetFormat`カスタム文字列を初期化します。 詳細については、「[日時指定コントロールでのカスタム書式指定文字列の使用](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)」を参照してください。 カスタム書式指定文字列を設定する一般的な場所は`OnInitDialog`、含まれているビュー クラスの`OnInitialUpdate`ダイアログ クラスまたは関数の関数にあります。

## <a name="handling-the-dtn_formatquery-notification"></a>DTN_FORMATQUERY通知の処理

コントロールが書式文字列を解析してコールバック フィールドを検出すると、アプリケーションはDTN_FORMATを送信し、通知メッセージDTN_FORMATQUERYします。 コールバック フィールド文字列は通知に含まれるため、どのコールバック フィールドが照会されているかを判断できます。

DTN_FORMATQUERY通知は、現在のコールバック フィールドに表示される文字列の最大許容サイズ (ピクセル単位) を取得するために送信されます。

この値を正しく計算するには、コントロールの表示フォントを使用して、フィールドの代わりに文字列の高さと幅を計算する必要があります。 文字列の実際の計算は、[関数の呼](/windows/win32/api/wingdi/nf-wingdi-gettextextentpoint32w)び出しで簡単に実現できます。 サイズが決定されたら、値をアプリケーションに戻し、ハンドラー関数を終了します。

次の例は、コールバック文字列のサイズを指定する方法の 1 つです。

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

現在のコールバック フィールドのサイズを計算したら、フィールドに値を指定する必要があります。 これは、DTN_FORMAT通知のハンドラーで行われます。

## <a name="handling-the-dtn_format-notification"></a>DTN_FORMAT通知の処理

DTN_FORMAT通知は、置換される文字列を要求するためにアプリケーションによって使用されます。 次の例は、1 つの可能なメソッドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
> **NMDATETIMEFORMAT**構造体へのポインターは、通知ハンドラーの最初のパラメーターを適切なタイプにキャストすることによって検出されます。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
