---
description: 詳細については、「コンパイラエラー C2567」を参照してください。
title: コンパイラ エラー C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 113dfebc1ac6bde6857ea55fd6249fff12c9faae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209114"
---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567

' file ' でメタデータを開くことができません。ファイルが削除または移動された可能性があります

ソースで参照されたメタデータファイル (を含む) が、コンパイラの `#using` フロントエンドプロセスと同じディレクトリに、コンパイラのバックエンドプロセスによって見つかりませんでした。 詳細については、 [#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md) を参照してください。

C2567 は、1台のコンピューターで **/c** を使用してコンパイルし、別のコンピューターでリンク時のコード生成を試行した場合に発生する可能性があります。 詳細については、「 [/ltcg (リンク時のコード生成)](../../build/reference/ltcg-link-time-code-generation.md)」を参照してください。

また、コンピューターにメモリが不足していることを示している場合もあります。

このエラーを修正するには、メタデータファイルがビルドプロセスのすべてのフェーズで同じディレクトリの場所にあることを確認してください。
