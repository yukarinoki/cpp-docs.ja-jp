---
title: ダイアログ エディター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39c34487941ee45f91883ed91b1faa2c93973cfe
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601725"
---
# <a name="dialog-editor"></a>ダイアログ エディター

**ダイアログ**エディターでは、作成またはダイアログ ボックスのリソースを編集することができます。 ダイアログ エディターでダイアログの .rc ファイルをダブルクリックして開く、**リソース ビュー**ウィンドウ (**ビュー** > **リソース ビュー**)。 なお**リソース ビュー** Express エディションでは使用できません。

ダイアログ ボックスまたはダイアログ ボックス テンプレートを新規作成する場合の最初のステップの 1 つは、ダイアログ ボックスにコントロールを追加することです。 **ダイアログ** ダイアログ ボックス内で作業するには、約に移動するか、エディター、特定のサイズ、形状、または配置に合わせてコントロールを配置することができます。 また、コントロールは簡単に削除できます。

ダイアログ ボックスをテンプレートとして格納すると、後で再利用できます。 また、ダイアログ ボックスのデザインと実装コードの編集の間の切り替えも簡単です。

さらに、ダイアログ エディターでは、単一または複数のコントロールのプロパティを編集できます。 タブ オーダーを変更することができます、つまり、フォーカス コントロールを取得する順序、**タブ**キーが押された、またはユーザーがキーボードを使用してコントロールを選択できるアクセス キー (キーの組み合わせ) を定義することができます。 事前に設定されているアクセス キーの一覧については、「 [ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)」を参照してください。

**ダイアログ**エディターでは ActiveX コントロールなどのカスタム コントロールを使用することもできます。 さらに、 [フォーム ビュー](../mfc/reference/cformview-class.md)、 [レコード ビュー](../data/record-views-mfc-data-access.md)、または [ダイアログ バー](../mfc/dialog-bars.md)も編集できます。

Visual Studio 2015 以降では、ダイアログ エディターを使用して、コントロールの移動方法と、ユーザーがダイアログをサイズ変更時にサイズを変更する方法を指定する、動的なレイアウトを定義します。 詳細については、「 [Dynamic Layout](../mfc/dynamic-layout.md)」を参照してください。

- [ダイアログ ボックスの新規作成](../windows/creating-a-new-dialog-box.md)

- [ユーザーが実行時に終了できないダイアログ ボックスの作成](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [[ダイアログ エディター] ツール バーの表示と非表示](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

- [ダイアログ エディターとコードの切り替え](../windows/switching-between-dialog-box-controls-and-code.md)

- [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)

- [ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [ダイアログ ボックスのテスト](../windows/testing-a-dialog-box.md)

- [ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)

- [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > 使用しているときに、**ダイアログ**エディターの多くの場合で、頻繁に使用されるコマンドのショートカット メニューを表示する、マウスの右ボタンをクリックすることができます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)  
[コントロール](../mfc/controls-mfc.md)  
[コントロール クラス](../mfc/control-classes.md)  
[ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)  
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)