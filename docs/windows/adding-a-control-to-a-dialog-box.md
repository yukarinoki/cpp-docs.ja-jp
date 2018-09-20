---
title: コントロールの追加 ダイアログ ボックス (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding controls to
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ad87e80d3301eaeda7a0599c3e484046092ed60
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446466"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>コントロールの追加 ダイアログ ボックス (C++)

### <a name="to-add-a-control-to-a-dialog-box"></a>ダイアログ ボックスにコントロールを追加するには

1. ダイアログ ボックスのタブ付きウィンドウがエディター フレーム内の現在のドキュメントであることを確認します。 ダイアログが現在のドキュメントでない場合は、 **ツールボックス** に **[ダイアログ エディター] タブ**が表示されません。

2. [[ツールボックス] ウィンドウ](../windows/dialog-editor-tab-toolbox.md) の [[ダイアログ エディター] タブ](/visualstudio/ide/reference/toolbox)で、必要なコントロールを選びます。

   - ダイアログ ボックス内で、コントロールを配置する位置をクリックします。 クリックした位置にコントロールが表示されます。 詳しくは、「 [複数のコントロールの追加](../windows/adding-multiple-controls.md)」をご覧ください。

       \- または -

   - ドラッグ アンド ドロップのコントロール、**ツールボックス**ウィンドウ、ダイアログ ボックス上の場所にします。 詳しくは、「 [コントロールの追加時のサイズ変更](../windows/sizing-a-control-while-you-add-it.md)」をご覧ください。

       \- または -

   - コントロールをダブルクリック、**ツールボックス**ウィンドウ (ダイアログ ボックスに表示) したい場所にコントロールを再配置します。

使用できるコントロールの種類については、**ツールボックス**ウィンドウを参照してください[ダイアログ エディタータブ、[ツールボックス] ウィンドウ](../windows/dialog-editor-tab-toolbox.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)