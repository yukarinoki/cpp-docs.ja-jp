---
title: メニュー コマンドと MFC アプリケーションのステータス バーのテキストとの関連付け
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
ms.openlocfilehash: fc39695358a9c1f2f62878487a5e4fedf5db2b82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468888"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>メニュー コマンドと MFC アプリケーションのステータス バーのテキストとの関連付け

MFC アプリケーションでは、各ユーザーが選択メニュー コマンドの説明のテキストを表示できます。 各メニュー コマンドを使用するテキスト文字列を割り当てることで、これを行う、**プロンプト**プロパティ、**プロパティ**ウィンドウ。 コマンドと同じ ID を持つ [ストリング テーブル](../windows/string-editor.md) に文字列がある場合、MFC アプリケーションでは、ユーザーがマウス ポインターをメニュー項目の上に置くと、実行中のアプリケーションのステータス バーにこの文字列リソースが自動的に表示されます。

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>メニュー コマンドをステータス バーのテキスト文字列に関連付けるには

1. **メニュー** エディターで、メニュー コマンドを選択します。

2. [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、関連付けるステータス バーのテキストを **[プロンプト]** ボックスに入力します。

## <a name="requirements"></a>必要条件

MFC

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[メニューへのコマンドの追加](../windows/adding-commands-to-a-menu.md)<br/>
[メニュー エディター](../windows/menu-editor.md)