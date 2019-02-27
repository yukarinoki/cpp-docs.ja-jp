---
title: ATL の定義済みシンボル
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
ms.openlocfilehash: 16991746c5c858310466f7eebd91a8478d2dcc5c
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954849"
---
# <a name="atl-predefined-symbols"></a>ATL の定義済みシンボル

これらのシンボルは、ATL ヘッダー ファイルで定義されているが、標準の Windows アプリケーションの関数とアクションをサポートします。 これらのシンボルは、ダイアログ ボックスが主に使用されます。

ダイアログとコントロールを使用する場合に、[ダイアログ エディター](../windows/dialog-editor.md)にこれらのシンボルが表示されます、**プロパティ**コモン コントロールに関連付けられているウィンドウ。 たとえば、ダイアログ ボックスがある場合、**キャンセル**ボタン、コマンドは IDCANCEL シンボルに関連付けられますことで、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)。

|||
|-|-|
|IDABORT|(コントロール)ダイアログ ボックスで、中止 ボタン|
|IDC_STATIC|(コントロール)スタティック コントロール|
|IDCANCEL|(コントロール)ダイアログ ボックスで、[キャンセル] ボタン|
|IDIGNORE|(コントロール)ダイアログ ボックスで、[無視] ボタン|
|IDNO|(コントロール)ダイアログ ボックスで、 ボタンがないです。|
|IDOK|(コントロール)ダイアログ ボックスで、[ok] ボタン|
|IDR_ACCELERATOR1|(リソース)アクセラレータ テーブル|
|IDRETRY|(コントロール)ダイアログ ボックスで、[再試行] ボタン|
|IDS_PROJNAME|(string)現在のアプリケーション名|
|IDYES|(コントロール)ダイアログ ボックスで、[はい] ボタン|

## <a name="requirements"></a>必要条件

ATL

## <a name="see-also"></a>関連項目

[定義済みシンボル ID](../windows/predefined-symbol-ids.md)<br/>
[MFC の定義済みシンボル](../windows/mfc-predefined-symbols.md)<br/>
[Win32 の定義済みシンボル](../windows/win32-predefined-symbols.md)<br/>