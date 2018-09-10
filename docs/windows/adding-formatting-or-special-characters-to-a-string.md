---
title: 文字列リソース (C++) への書式設定や特殊文字の追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bf67723f516e0c5b1bf9931d7f53d36907fca86
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313391"
---
# <a name="adding-formatting-or-special-characters-to-a-string-resource-c"></a>(C++) の文字列リソースへの書式設定や特殊文字を追加します。

### <a name="to-add-formatting-or-special-characters-to-a-string"></a>文字列に書式設定や特殊文字を追加するには

1. アイコンをダブルクリックして、文字列テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 変更する文字列を選択します。

3. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、内のテキストには以下の標準のエスケープ シーケンスのいずれかの追加、**キャプション**ボックスで、キーを押します**Enter**します。

   |これを取得するには|入力します。|
   |-----------------|---------------|
   |改行|\n|
   |キャリッジ リターン|\r|
   |タブ|\t|
   |円記号 (\\)|\\\|
   |ASCII 文字|\ddd (8 進表記)|
   |警告 (ベル)|\a|

> [!NOTE]
> **文字列**エディターが ASCI のエスケープ文字の完全なセットをサポートしていません。 上記のリストにのみ使用できます。

マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、次を参照してください。[チュートリアル: Windows フォームのローカリゼーション](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\))します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ストリング エディター](../windows/string-editor.md)  