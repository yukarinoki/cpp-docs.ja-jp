---
title: ダイアログ エディター タブ、ツールボックス (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b6e05e654b66c2178b7dc6e772c95df89512d1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399848"
---
# <a name="dialog-editor-tab-toolbox-c"></a>ダイアログ エディター タブ、ツールボックス (C++)

**ダイアログ エディター**タブに表示されます、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)作業するとき、**ダイアログ**エディター。 を、新しいダイアログ ボックスにコントロールを追加するには、からコントロールをドラッグ、**ツールボックス** ダイアログ ボックスを作成する (詳細については、次を参照してください。 [ ダイアログ ボックスにコントロールを追加](adding-a-control-to-a-dialog-box.md))。 次いでコントロールの移動、またはサイズと形状の変更ができます。

使用できる標準のコントロール、**ツールボックス**は。

- [ボタン コントロール](../mfc/reference/cbutton-class.md)

- [チェック ボックス コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [コンボ ボックス コントロール](../mfc/reference/ccombobox-class.md)

- [コントロールを編集します。](../mfc/reference/cedit-class.md)

- グループ ボックス

- [リスト ボックス コントロール](../mfc/reference/clistbox-class.md)

- [ラジオ ボタン コントロール](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [スタティック テキスト コントロール](../mfc/reference/cstatic-class.md)

- [画像コントロール](../mfc/reference/cpictureholder-class.md)

- [リッチ エディット 2.0 コントロール](../mfc/using-cricheditctrl.md)

- [スクロール バー コントロール](../mfc/reference/cscrollbar-class.md)

[Windows コモン コントロール](../mfc/controls-mfc.md)で使用できる、**ツールボックス**アプリケーションで高度な機能を提供します。 Windows コモン コントロールには以下が含まれます。

- [スライダー コントロール](../mfc/slider-control-styles.md)

- [スピン コントロール](../mfc/using-cspinbuttonctrl.md)

- [プログレス コントロール](../mfc/styles-for-the-progress-control.md)

- [ホット キー コントロール](../mfc/using-a-hot-key-control.md)

- [リスト コントロール](../mfc/list-control-and-list-view.md)

- [ツリー コントロール](../mfc/tree-control-styles.md)

- [タブ コントロール](../mfc/tab-controls-and-property-sheets.md)

- [アニメーション コントロール](../mfc/using-an-animation-control.md)

- [日時指定コントロール](../mfc/creating-the-date-and-time-picker-control.md)

- [月間予定表コントロールします。](../mfc/month-calendar-control-examples.md)

- [IP アドレス コントロール](../mfc/reference/cipaddressctrl-class.md)

- [拡張コンボ ボックス コントロール](../mfc/creating-an-extended-combo-box-control.md)

- [カスタム コントロール](custom-controls-in-the-dialog-editor.md)

ダイアログ ボックスにカスタム コントロールを追加するには選択して、**カスタム コントロール**アイコン、**ツールボックス**ダイアログ ボックスにドラッグするとします。 追加する、 **Syslink**を制御し、カスタム コントロールを追加、変更、コントロールの**クラス**プロパティを**Syslink**します。 これにより、プロパティを更新し、表示、 **Syslink**プロパティを制御します。 MFC ラッパー クラスについては、次を参照してください。 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)します。

必要な場合も[、ダイアログ ボックスに ActiveX コントロールを追加](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)します。

カスタマイズすることも、**ツールボックス**ウィンドウを簡単に使用します。 詳細については、「[ツールボックスの使用](/visualstudio/ide/using-the-toolbox)」を参照してください。

使用しての詳細については、 **RichEdit 1.0** MFC でコントロールを参照してください[MFC での RichEdit 1.0 コントロールの使用](../windows/using-the-richedit-1-0-control-with-mfc.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)<br/>
[コントロール クラス](../mfc/control-classes.md)<br/>
[ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)<br/>
[スクロール バー スタイル](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[リッチ エディット コントロールの例](../mfc/rich-edit-control-examples.md)<br/>
[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)