---
title: 日付と時刻の選択のコールバック フィールドを使用してコントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b0d59aa8c30e9308448467bb198e898106e61f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383787"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>日時指定コントロールでのコールバック フィールドの使い方
日付と時刻の選択フィールドを定義する標準書式文字、に加えてコールバック フィールドとして、カスタム書式指定文字列の特定の部分を指定することによって、出力をカスタマイズできます。 コールバック フィールドを宣言するには、1 つまたは複数の"X"文字 (ASCII コード 88) を書式指定文字列の本文に任意の場所含めます。 たとえば、次の文字列"' は現在: 'yy '/' MM '/' dd' (日 'X')'"により、年、月、日、および最後に、年の日付を続けてとして現在の値を表示する日付と時刻のピッカー コントロール。  
  
> [!NOTE]
>  数 X コールバックでは、フィールドは表示される文字の数に対応しません。  
  
 "X"文字の繰り返しによって、カスタムの文字列での複数のコールバック フィールドを区別することができます。 したがって、書式設定文字列"XXddddMMMdd'、' yyyXXX"、"XX"と"XXX"の 2 つの一意のコールバック フィールドが含まれています。  
  
> [!NOTE]
>  コールバック フィールドが有効なフィールドとして扱われるを処理するアプリケーションを準備する必要がありますので**DTN_WMKEYDOWN**通知メッセージです。  
  
 日付と時刻ピッカー コントロールでのコールバック フィールドの実装は、3 つの部分で構成されます。  
  
-   カスタム書式指定文字列の初期化  
  
-   処理、 **DTN_FORMATQUERY**通知  
  
-   処理、 **DTN_FORMAT**通知  
  
## <a name="initializing-the-custom-format-string"></a>カスタム書式指定文字列の初期化  
 呼び出しを含むカスタムの文字列を初期化`CDateTimeCtrl::SetFormat`です。 詳細については、次を参照してください。[日付と時刻の選択コントロールのカスタム書式指定文字列を使用して](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)です。 カスタム書式指定文字列を設定する一般的な場所は、`OnInitDialog`を含むダイアログ クラスの関数または`OnInitialUpdate`を含むビュー クラスの関数。  
  
## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY 通知の処理  
 コントロールは、書式指定文字列を解析し、コールバック フィールドを検出すると、アプリケーションが送信**DTN_FORMAT**と**DTN_FORMATQUERY**通知メッセージです。 コールバック フィールドの文字列は、どのコールバック フィールドのクエリが実行されるかを特定できるように通知と共にです。  
  
 **DTN_FORMATQUERY**を現在のコールバック フィールドに表示される文字列のピクセル単位の最大許容サイズを取得する通知を送信します。  
  
 この値を正しく計算するには、必要がありますを計算する、フィールドの代わりに使用する、文字列の幅と高さコントロールの表示フォントを使用します。 呼び出して、文字列の実際の計算を簡単に行う、 [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) Win32 関数。 サイズが特定されると、値をアプリケーションに渡すし、ハンドラー関数を終了します。  
  
 次の例では、コールバックの文字列のサイズを指定する 1 つの方法を示します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 現在のコールバック フィールドのサイズが計算された後は、フィールドの値を指定してください。 これは、ハンドラーで、 **DTN_FORMAT**通知します。  
  
## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT 通知の処理  
 **DTN_FORMAT**通知が置換される文字の文字列を要求するアプリケーションで使用します。 次の例では、1 つの可能なメソッドを示しています。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  ポインター、 **NMDATETIMEFORMAT**通知ハンドラーが適切な型への最初のパラメーターをキャストして構造が検出されます。  
  
## <a name="see-also"></a>関連項目  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

