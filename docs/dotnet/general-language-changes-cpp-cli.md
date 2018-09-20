---
title: 言語の変更の概要 (C +/cli CLI) |Microsoft Docs
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
ms.openlocfilehash: 9b48ebdf0bf25399b08f8a1cb1240a857cfad352
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418464"
---
# <a name="general-language-changes-ccli"></a>言語の変更の概要 (C++/CLI)

Visual c、c++ マネージ拡張から変更 CLR 言語機能の数。

このセクションで説明されている変更は、言語のちょっとしたテクニックの一種です。 文字列リテラル、オーバー ロードの解決、省略記号の間での変更の処理に変更が含まれています、`Param`属性の変更`typeof`に`typeid`、コンス トラクター初期化子リストでは、呼び出し元の変更と新しいキャスト表記法の概要の`safe_cast`します。

[リテラル文字列](../dotnet/string-literal.md)<br/>
リテラル文字列の処理がどのように変更されたかについて説明します。

[パラメーター配列と省略記号](../dotnet/param-array-and-ellipsis.md)<br/>
について説明する方法`ParamArray`省略記号の優先順位が指定されたが (`...`) のさまざまな数の引数を持つ関数呼び出しを解決します。

[typeof から T::typeid への移行](../dotnet/typeof-goes-to-t-typeid.md)<br/>
について説明しますが、どのように`typeof`演算子が置き換わりましたされて`typeid`します。

[初期化子リスト](../dotnet/initializer-lists.md)<br/>
初期化子リストの呼び出しの順序の変更について説明します。

[キャスト表記と safe_cast<> の導入](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<br/>
キャスト表記と特定の変更の概要を説明します`safe_cast`します。

## <a name="see-also"></a>関連項目

[C++/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)