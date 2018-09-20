---
title: ダイアログのコントロールを追加するダイアログ ボックスは不要になった機能 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89e4a639ad953593195401fe2eadeb5d7877a160
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445867"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function-c"></a>ダイアログのコントロールを追加するダイアログ ボックスは不要になった機能 (C++)

ダイアログ ボックスに、一般的なコントロールまたはリッチ エディット コントロールを追加すると、ダイアログ ボックスのテストまたはダイアログ自体は表示されないときにいない表示されます。

### <a name="example-of-the-problem"></a>問題の例

1. Windows アプリケーション (コンソール アプリケーションではなく) を作成するためにアプリケーション設定を変更する、Win32 プロジェクトを作成します。

2. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルをダブルクリックします。

3. ダイアログのオプションでダブルクリックして、**について**ボックス。

4. 追加、 **IP アドレス コントロール** ダイアログ ボックス。

5. 保存と**すべてリビルド**します。

6. プログラムを実行します。

7. ダイアログ ボックスの**ヘルプ** メニューのをクリックして、**について**コマンド; ダイアログ ボックスが表示されます。

### <a name="the-cause"></a>原因

現時点では、ダイアログ エディターが自動的に追加コードをプロジェクトにリッチ エディット コントロールをダイアログ ボックスにドラッグ アンド ドロップ、次の一般的なコントロールまたは。 Visual Studio はエラーまたは警告がこの問題が発生します。 コントロールのコードを手動で追加する必要があります。

||||
|-|-|-|
|スライダー コントロール|ツリー コントロール|Date Time Picker|
|スピン コントロール|タブ コントロール|月間予定表|
|プログレス コントロール|アニメーション コントロール|IP アドレスの管理|
|ホット キー|リッチ エディット コントロール|拡張コンボ ボックス|
|リスト コントロール|リッチ エディット 2.0 コントロール|カスタム コントロール|

## <a name="the-fix-for-common-controls"></a>コモン コントロール用の修正プログラム

コモン コントロール ダイアログ ボックスを使用するために呼び出す必要があります[InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex)または`AFXInitCommonControls` ダイアログ ボックスを作成する前にします。

## <a name="the-fix-for-richedit-controls"></a>リッチ エディット コントロールの修正プログラム

呼び出す必要があります`LoadLibrary`リッチ エディット コントロールの。 詳細については、次を参照してください。 [MFC での RichEdit 1.0 コントロールの使用](../windows/using-the-richedit-1-0-control-with-mfc.md)、[リッチのエディット コントロールについて](/windows/desktop/Controls/about-rich-edit-controls)、Windows sdk と[リッチ エディット コントロールの概要](../mfc/overview-of-the-rich-edit-control.md)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)