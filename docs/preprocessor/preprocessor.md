---
title: プリプロセッサ
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 7188d7a6803c9eec109a59906cf0c016a460819d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337504"
---
# <a name="preprocessor"></a>プリプロセッサ

プリプロセッサは、変換の第 1 段階としてソース ファイルのテキストを操作するテキスト プロセッサです。 プリプロセッサはソーステキストを解析しませんが、マクロ呼び出しを見つけるためにトークンに分割します。 コンパイラは通常、最初のパスでプリプロセッサを呼び出しますが、コンパイルすることなくテキストを処理するために個別にプリプロセッサを呼び出すことができます。

プリプロセッサのリファレンス資料として、次のセクションを参照してください。

- [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)

- [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)

- [定義済みマクロ](../preprocessor/predefined-macros.md)

- [プラグマ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**マイクロソフト固有**

プリプロセス後にソース コードの一覧を取得するには[、/E](../build/reference/e-preprocess-to-stdout.md)または[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)コンパイラ オプションを使用します。 どちらのオプションもプリプロセッサを呼び出し、結果のテキストを標準出力デバイスに送信します。 2 つのオプションの違いは`/E`、`#line`ディレクティブを含む`/EP`、およびこれらのディレクティブを取り除くです。

**エンド マイクロソフト 固有**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a>特殊な用語

プリプロセッサのドキュメントでは、"引数" という用語は、関数に渡されるエンティティを意味します。 場合によっては、関数呼び出しで指定された引数式と、関数定義で指定された引数宣言を記述する "actual" または "formal" によって変更されることもあります。

"変数" という用語は、簡単な C 型のデータ オブジェクトを意味します。 "オブジェクト" という用語は、C++ オブジェクトと変数の両方を指します。それは包括的な用語です。

## <a name="see-also"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)\
[翻訳のフェーズ](../preprocessor/phases-of-translation.md)
