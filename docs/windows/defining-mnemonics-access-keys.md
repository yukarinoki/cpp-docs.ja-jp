---
title: ニーモニック (アクセス キー) の定義 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d707b0205c3f13954681eb4f6a033496a2997ce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425796"
---
# <a name="defining-mnemonics-access-keys"></a>ニーモニック (アクセス キー) の定義

通常、キーボード ユーザーが入力フォーカスを移動 1 つのコントロールからを別のダイアログ ボックスで、**タブ**と**矢印**キー。 ただし、ユーザーを 1 つのキーを押して、コントロールを選択できるようにするアクセス キー (ニーモニックまたは覚えやすい名前) を定義することができます。

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>(プッシュ ボタン、チェック ボックス、ラジオ ボタン)、表示されるキャプションを使用して、コントロールのアクセス キーを定義するには

1. ダイアログ ボックスで、コントロールを選択します。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)の**キャプション**プロパティ、アンパサンドを入力する、コントロールの新しい名前を入力 (`&`) そのコントロールのアクセス キーとして使用文字の前にします。 たとえば、`&Radio1` のようにします。

3. **Enter** キーを押します。

   下線が表示されるキャプションをアクセス キーを示すために表示されます**R**adio1 します。

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>表示されるキャプションを持たないコントロールのアクセス キーを定義するには

1. 使用して、コントロールのキャプションを行う、**静的テキスト**を制御、[ツールボックス](/visualstudio/ide/reference/toolbox)します。

2. 静的なテキスト キャプションのアンパサンドを入力します (`&`) へのアクセス キーとして使用文字の前にします。

3. 静的なテキスト コントロールの直前に、コントロールがタブ オーダー内でラベルを付けることを確認します。

ダイアログ ボックス内のすべてのアクセス キーは一意である必要があります。

### <a name="to-check-for-duplicate-access-keys"></a>重複するアクセス キーを確認するには

1. **形式** メニューのをクリックして**ニーモニックの確認**します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)