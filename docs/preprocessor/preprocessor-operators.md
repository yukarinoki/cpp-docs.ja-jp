---
description: '詳細情報: プリプロセッサ演算子'
title: プリプロセッサ演算子
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 960531a32dd8b4f834117fb01272e2ed45fecf92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202094"
---
# <a name="preprocessor-operators"></a>プリプロセッサ演算子

ディレクティブのコンテキストでは、4つのプリプロセッサ固有の演算子が使用され `#define` ます。 各の概要については、次の表を参照してください。 文字列化、文字定数化、およびトークン連結演算子については、次の 3 つのセクションで説明します。 演算子の詳細については、 `defined` 「 [#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)」を参照してください。

|演算子|アクション|
|--------------|------------|
|[文字列化演算子 (#)](../preprocessor/stringizing-operator-hash.md)|対応する実引数が二重引用符で囲まれます|
|[文字定数化演算子 (#@)](../preprocessor/charizing-operator-hash-at.md)|対応する引数を単一引用符で囲み、文字として扱うようにします (Microsoft 固有)。|
|[トークン連結演算子 (##)](../preprocessor/token-pasting-operator-hash-hash.md)|実引数として使用されるトークンが、他のトークンを形成するために連結されることを許可します|
|[defined 演算子](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|特定のマクロ ディレクティブで複合式の記述を簡略化します|

## <a name="see-also"></a>関連項目

[プリプロセッサディレクティブ](../preprocessor/preprocessor-directives.md)\
[定義済みマクロ](../preprocessor/predefined-macros.md)\
[c/c + + プリプロセッサリファレンス](../preprocessor/c-cpp-preprocessor-reference.md)
