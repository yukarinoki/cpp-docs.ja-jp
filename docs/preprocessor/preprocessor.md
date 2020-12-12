---
description: '詳細情報: プリプロセッサ'
title: プリプロセッサ
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: dd79766777926871e7bbf849f96420ef37052eba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202081"
---
# <a name="preprocessor"></a>プリプロセッサ

プリプロセッサは、変換の第 1 段階としてソース ファイルのテキストを操作するテキスト プロセッサです。 プリプロセッサはソーステキストを解析しませんが、マクロ呼び出しを見つけるためにトークンに分割されます。 コンパイラは通常、最初のパスでプリプロセッサを呼び出しますが、コンパイルすることなくテキストを処理するために個別にプリプロセッサを呼び出すことができます。

プリプロセッサのリファレンス資料として、次のセクションを参照してください。

- [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)

- [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)

- [定義済みマクロ](../preprocessor/predefined-macros.md)

- [プラグマ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft 固有の仕様**

前処理の後、 [/e](../build/reference/e-preprocess-to-stdout.md) または [/ep](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) コンパイラオプションを使用して、ソースコードの一覧を取得できます。 どちらのオプションも、プリプロセッサを起動し、生成されたテキストを標準出力デバイス (ほとんどの場合、コンソール) に送信します。 2つのオプションの違いは、にディレクティブが含まれ、これらのディレクティブが除去されることです `/E` `#line` `/EP` 。

**Microsoft 固有の仕様はここまで**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a> 特別な用語

プリプロセッサのドキュメントでは、"引数" という用語は、関数に渡されるエンティティを意味します。 場合によっては、関数呼び出しで指定された引数式と関数定義で指定された引数宣言をそれぞれ記述する "actual" または "仮の" によって変更されることがあります。

"変数" という用語は、簡単な C 型のデータ オブジェクトを意味します。 "オブジェクト" という用語は、C++ オブジェクトと変数の両方を指します。これは包括的な用語です。

## <a name="see-also"></a>関連項目

[C/C++ のプリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)\
[変換フェーズ](../preprocessor/phases-of-translation.md)
