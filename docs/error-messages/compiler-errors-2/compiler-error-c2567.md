---
title: コンパイラ エラー C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 921992c678c1de0b74f99f544173478ebe809b2c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177457"
---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567

' file ' でメタデータを開くことができません。ファイルが削除または移動された可能性があります

ソース (`#using`) で参照されていたメタデータファイルが、コンパイラのフロントエンドプロセスと同様に、コンパイラのバックエンドプロセスによって同じディレクトリに見つかりませんでした。 詳細については、 [#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)を参照してください。

C2567 は、1台のコンピューターで **/c**を使用してコンパイルし、別のコンピューターでリンク時のコード生成を試行した場合に発生する可能性があります。 詳細については、「 [/ltcg (リンク時のコード生成)](../../build/reference/ltcg-link-time-code-generation.md)」を参照してください。

また、コンピューターにメモリが不足していることを示している場合もあります。

このエラーを修正するには、メタデータファイルがビルドプロセスのすべてのフェーズで同じディレクトリの場所にあることを確認してください。
