---
title: 一般的な言語の変更 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aede6cc0d4bd8e50d8662f301ffdfb7b6179a230
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109139"
---
# <a name="general-language-changes-ccli"></a>言語の変更の概要 (C++/CLI)
いくつかの CLR 言語の機能が Visual c、c++ マネージ拡張から変更します。  
  
 このセクションで説明されている変更は、言語その一種です。 文字列リテラル、省略記号の間でオーバー ロードの解決の変更の処理の変更が含まれますと`Param`属性の変更`typeof`に`typeid`、コンス トラクター初期化子リストの呼び出しで変更され、新しいキャスト表記法の概要の`safe_cast`します。  
  
 [リテラル文字列](../dotnet/string-literal.md)  
 リテラル文字列の処理がどのように変更されたかについて説明します。  
  
 [パラメーター配列と省略記号](../dotnet/param-array-and-ellipsis.md)  
 について説明する方法`ParamArray`は指定された優先順位、省略記号ボタン (`...`) さまざまな数の引数を持つ関数呼び出しを解決するためです。  
  
 [typeof から T::typeid への移行](../dotnet/typeof-goes-to-t-typeid.md)  
 について説明しますが、どのように`typeof`に演算子が置き換わる可能性されて`typeid`です。  
  
 [初期化子リスト](../dotnet/initializer-lists.md)  
 初期化子リストの呼び出しの順序の変更について説明します。  
  
 [キャスト表記と safe_cast<> の導入](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 キャスト表記と特定の変更の概要を説明`safe_cast`です。  
  
## <a name="see-also"></a>関連項目  
 [C++/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)