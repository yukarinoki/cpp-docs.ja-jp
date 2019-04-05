---
title: プリプロセッサ
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: b1443d88fdba470cb8ed5058c9a9012bfbdc5bc7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028575"
---
# <a name="preprocessor"></a>プリプロセッサ
プリプロセッサは、変換の第 1 段階としてソース ファイルのテキストを操作するテキスト プロセッサです。 プリプロセッサは、ソース テキストを解析しませんが、マクロの呼び出しを特定する目的でトークンに分割します。 コンパイラは通常、最初のパスでプリプロセッサを呼び出しますが、コンパイルすることなくテキストを処理するために個別にプリプロセッサを呼び出すことができます。

プリプロセッサのリファレンス資料として、次のセクションを参照してください。

- [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)

- [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)

- [定義済みマクロ](../preprocessor/predefined-macros.md)

- [プラグマ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft 固有の仕様**

使用して前処理した後、ソース コードの一覧を取得することができます、 [/E](../build/reference/e-preprocess-to-stdout.md)または[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)コンパイラ オプション。 両オプション共に、プリプロセッサを呼び出し、生成されるテキストを標準出力デバイス (ほとんどの場合、コンソール) に出力します。 2 つのオプション間の違いは、/E では `#line` ディレクティブが含まれ、/EP ではこうしたディレクティブが削除されることです。

**END Microsoft 固有の仕様**

##  <a name="_predir_special_terminology"></a> 特別な用語

プリプロセッサのドキュメントでは、"引数" という用語は、関数に渡されるエンティティを意味します。 場合によっては、関数呼び出しで指定される引数式、および関数定義で指定される引数宣言をそれぞれ表す "実" または "仮" を修飾として先頭に付けることがあります。

"変数" という用語は、簡単な C 型のデータ オブジェクトを意味します。 "オブジェクト" は、C++ オブジェクトおよび変数の両方を意味する包括的な用語です。

## <a name="see-also"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[変換フェーズ](../preprocessor/phases-of-translation.md)