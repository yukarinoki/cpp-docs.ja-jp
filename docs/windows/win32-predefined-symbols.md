---
title: Win32 の定義済みのシンボル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], predefined symbols
- symbols [C++], Win32 predefined
- Windows API [C++], predefined symbols
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18edb56c03541f61607817d14fdbadb067a3630d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422780"
---
# <a name="win32-predefined-symbols"></a>Win32 の定義済みシンボル

これらのシンボルは、Win32 のヘッダー ファイルで定義され、標準の Windows アプリケーションの関数とアクションをサポートします。 これらのシンボルは主に、共通の UI 要素を使用します。 これらのシンボルが表示されます、リソース エディター内のコントロールを使用する場合、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)コモン コントロールに関連付けられています。 たとえば、アプリケーションのアイコンがツールバーに表示する場合、アイコンに関連付けるシンボル IDI_SMALL で、**プロパティ ウィンドウ**します。

|||
|-|-|
|IDABORT|コントロール: ダイアログ ボックスの [中止] ボタン|
|IDC_STATIC|ダイアログ ボックスで静的なテキストを制御:|
|IDCANCEL|制御: ダイアログ ボックスの [キャンセル] ボタン|
|IDD_ABOUTBOX|ダイアログ ボックスの詳細 ダイアログ ボックス: 製品|
|IDI_PROJECTNAME|アイコン: 現在のプロジェクト アイコン|
|IDI_SMALL|アイコン: 現在のプロジェクトの小さいアイコン|
|IDIGNORE|ダイアログ ボックス [無視] ボタンに使用される制御。|
|IDM_ABOUT|: メニュー項目は、ヘルプで使用しています.に関しては...|
|IDM_EXIT|メニュー項目: は、ファイルと共に使用しています.終了しています.|
|IDNO|制御: ダイアログ ボックスの [いいえ] ボタン|
|IDOK|コントロール: ダイアログ ボックスの [OK] ボタン|
|IDRETRY|制御: ダイアログ ボックスの [再試行] ボタン|
|IDS_APP_TITLE|現在のアプリケーション名を文字列:|
|IDYES|制御: ダイアログ ボックスの はい ボタンします。|

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[定義済みシンボル ID](../windows/predefined-symbol-ids.md)<br/>
[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)