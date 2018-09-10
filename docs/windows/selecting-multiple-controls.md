---
title: 複数のコントロールの選択 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- controls [C++], removing from groups
ms.assetid: efbdbade-0a3a-4328-b36e-a6376c06e8de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6789a378b163da9e3cefbabb506f84a3cb9a5d7f
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317780"
---
# <a name="selecting-multiple-controls"></a>複数のコントロールの選択

### <a name="to-select-multiple-controls"></a>複数のコントロールを選択するには

1. [ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)を選択、**ポインター**ツール。

2. 選択ボックスで、ダイアログ ボックスで選択するコントロールの周囲へのポインターをドラッグします。

   マウス ボタンを離すと、すべて内側と、選択ボックスが選択されているを交差を制御します。

   \- または -

- 押しながら、 **Shift**キーを選択したいコントロールをクリックします。

   \- または -

- 押しながら、 **Ctrl**キーを選択したいコントロールをクリックします。

### <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>コントロールを選択したコントロールのグループから削除するには、か、コントロールを選択したコントロールのグループに追加するには

1. 押しながら選択コントロールのグループと、 **Shift**キーし、既存の選択範囲を追加または削除するコントロールをクリックします。

   > [!NOTE]
   > 押しながら、 **Ctrl**キーと、選択範囲内のコントロールをクリックするとその選択範囲内の主要なコントロールを制御する、します。 詳細については、次を参照してください。[主要なコントロールを指定する](../windows/specifying-the-dominant-control.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[コントロールの選択](../windows/selecting-controls.md)  
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)