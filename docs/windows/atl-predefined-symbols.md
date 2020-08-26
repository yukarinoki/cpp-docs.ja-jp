---
title: ATL の定義済みシンボル
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
ms.openlocfilehash: 8134f334b0143a360fd3e02c04bca7a65ce67ce0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836388"
---
# <a name="atl-predefined-symbols"></a>ATL の定義済みシンボル

これらのシンボルは ATL ヘッダーファイルで定義されていますが、標準の Windows アプリケーション関数とアクションをサポートしています。 これらのシンボルは、主にダイアログボックスと共に使用されます。

[ダイアログエディターでダイアログ](dialog-editor.md)とコントロールを操作しているときに、これらのシンボルは、コモンコントロールに関連付けられている[プロパティウィンドウ](/visualstudio/ide/reference/properties-window)に表示されます。 たとえば、ダイアログボックスに **[キャンセル** ] ボタンがある場合、そのコマンドは [ **プロパティ** ] ウィンドウのシンボル IDCANCEL に関連付けられます。

|名前|説明|
|-|-|
|IDABORT|制御ダイアログボックス、[中止] ボタン|
|IDC_STATIC|制御スタティックコントロール|
|IDCANCEL|制御ダイアログボックス、[キャンセル] ボタン|
|IDIGNORE|制御ダイアログボックス、[無視] ボタン|
|IDNO|制御ダイアログボックス、[いいえ] ボタン|
|IDOK|制御ダイアログボックスの [OK] ボタン|
|IDR_ACCELERATOR1|センターアクセラレータテーブル|
|IDRETRY|制御ダイアログボックスの [再試行] ボタン|
|IDS_PROJNAME|文字列現在のアプリケーション名|
|IDYES|制御ダイアログボックス、[はい] ボタン|

## <a name="requirements"></a>必要条件

ATL

## <a name="see-also"></a>関連項目

[定義済みのシンボル Id](predefined-symbol-ids.md)<br/>
[MFC の定義済みシンボル](mfc-predefined-symbols.md)<br/>
[Win32 の定義済みシンボル](win32-predefined-symbols.md)<br/>
