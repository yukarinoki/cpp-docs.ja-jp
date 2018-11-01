---
title: ツール ヒント (C++) のツール バー ボタンの作成
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
ms.openlocfilehash: 9179dfcc47f69b9f5db131467f0216da6363085c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558007"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button-c"></a>ツール ヒント (C++) のツール バー ボタンの作成

### <a name="to-create-a-tool-tip"></a>ツール ヒントを作成するには

1. ツール バー ボタンを選択します。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)の**プロンプト**プロパティ フィールドをステータス バーのメッセージが表示されたら、ボタンの説明を追加、`\n`とツール ヒントの名前。

ツール ヒントの一般的な例は、**印刷**ボタン**ワードパッド**:

1. 開いている**ワードパッド**します。

2. マウス ポインターを合わせ、**印刷**ツールバー ボタンをクリックします。

3. 注意して、word`Print`マウス ポインターの下浮動ようになりました。

4. ステータス バーを見て (の一番下にある、**ワードパッド**ウィンドウ) のようになりました、テキストを表示することが通知`Prints the active document`します。

`Print`で**手順 3** 「ツール ヒント名」は、および`Prints the active document`から**手順 4** 「の説明、ステータス バーのボタンをクリックします」。

この効果を使用する場合、**ツールバー**エディター、設定、**プロンプト**プロパティを`Prints the active document\nPrint`します。

> [!NOTE]
> プロンプトのテキストを使用して編集することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[ツール バー ボタンの作成、移動、および編集](../windows/creating-moving-and-editing-toolbar-buttons.md)<br/>
[ツール バー エディター](../windows/toolbar-editor.md)