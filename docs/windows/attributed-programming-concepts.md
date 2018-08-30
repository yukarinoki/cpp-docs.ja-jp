---
title: 属性プログラミングの概念 |Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributed programming [C++]
- attributes [C++]
- programming [C++], attributed programming
ms.assetid: 563e7e7c-65e1-44f4-b0b2-da04a6c1bc9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 223359e10ef0e64860a611079abf9e7e83a26fe1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222809"
---
# <a name="attributed-programming-concepts"></a>属性付きプログラミングの概念

Visual C には、さまざまな属性をプログラムで使用できるようにマテリアルが含まれています。 Visual C の新機能の属性は、COM プログラミングおよび .NET Framework 共通言語ランタイムの開発を容易に設計されています。 ソース ファイルで属性を追加するときに、コンパイラはプロバイダーのダイナミック リンク ライブラリ (DLL) コードを挿入または生成されたオブジェクト ファイル内のコードを変更するには機能します。 .Idl ファイル、インターフェイス、タイプ ライブラリ、およびその他の COM 要素の作成を支援する属性があります。 統合開発環境 (IDE) で属性は、[プロパティ] ウィンドウと、ウィザードによってサポートします。

属性は、COM オブジェクトを記述するために必要な詳細なコーディングの一部をなくすため中に、バック グラウンド必要があります。 [COM fundamentals](/windows/desktop/com/the-component-object-model)に最大限に活用します。

## <a name="in-this-section"></a>このセクションの内容

[属性の目的](../windows/purpose-of-attributes.md)  
属性付きプログラミングの概要を示します。

[属性の基本的なしくみ](../windows/basic-mechanics-of-attributes.md)  
プロジェクト内の属性の機能について説明します。

[属性付きプログラムの作成](../windows/building-an-attributed-program.md)  
プロジェクトでの C++ コンパイラ オプションの使用方法についてを説明します。

[属性のカテゴリ](../windows/attribute-categories.md)  
Visual C で使用される属性のカテゴリへのリンクを提供します。

[属性 Programmming に関する FAQ](../windows/attribute-programming-faq.md)  
回答では、質問が属性付きプログラミングに関してよく寄せられます。

## <a name="related-sections"></a>関連項目

[属性リファレンス](../windows/cpp-attributes-reference.md)  
個々 の属性とその使用を説明するリファレンス トピックへのリンクを提供します。

[挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)  
属性付きプログラムのデバッグについて説明します。

[_ _super](../cpp/super.md)と[_ _interface](../cpp/interface.md)  
新しい C++ のキーワードに関連する属性付きプログラミングへのリンク。