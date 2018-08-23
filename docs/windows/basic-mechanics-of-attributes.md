---
title: 属性の基本的なしくみ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75f30fbe64251e0fbb7fdb48f1d0a628ec4563b8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601226"
---
# <a name="basic-mechanics-of-attributes"></a>属性の基本的なしくみ

プロジェクトに属性を挿入する次の 3 つの方法はあります。 最初に挿入できますに手動でソース コード。 次に、プロジェクトでオブジェクトのプロパティ グリッドを使用してそれらを挿入できます。 最後に、さまざまなウィザードを使用してそれらを挿入できます。 使用しての詳細については、**プロパティ**ウィンドウとさまざまなウィザードを参照してください。 [Visual c プロジェクトの管理の作成と](../ide/creating-and-managing-visual-cpp-projects.md)します。

としてする前に、プロジェクトをビルドするとき、コンパイラ解析各 C++ ソース ファイルのオブジェクト ファイルを生成します。 ただし、コンパイラが属性を検出する場合は解析し、構文を検査します。 コンパイラに動的を呼び出してコードを挿入またはコンパイル時にその他の変更、属性プロバイダー。 プロバイダーの実装は、属性の型によって異なります。 たとえば、ATL 関連の属性は、Atlprov.dll によって実装されます。

次の図は、コンパイラと属性プロバイダー間のリレーションシップを示しています。

![コンポーネント属性コミュニケーション](../windows/media/vccompattrcomm.gif "vcCompAttrComm")

> [!NOTE]
> 属性の使用方法には、ソース ファイルの内容は変更されません。 属性が生成されたコードが表示される唯一の時間は、デバッグ セッション中には。 さらに、プロジェクト内の各ソース ファイルの属性を置換した結果を表示するテキスト ファイルを生成できます。 この手順の詳細については、次を参照してください。 [/Fx (挿入されたコードのマージ)](../build/reference/fx-merge-injected-code.md)と[挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)します。

ほとんどの C++ 構造体のような属性は、適切な使用方法を定義する一連の特性があります。 これは、操作を行うと、属性のコンテキストと呼ばは、属性コンテキストの表の各属性のリファレンス トピックで対処されます。 たとえば、[コクラス](../windows/coclass.md)属性のみ適用できますを既存のクラスまたは構造体ではなく、 [cpp_quote](../windows/cpp-quote.md)属性には、C++ ソース ファイル内のどこにでも挿入できます。

## <a name="see-also"></a>関連項目

[概念](../windows/attributed-programming-concepts.md)