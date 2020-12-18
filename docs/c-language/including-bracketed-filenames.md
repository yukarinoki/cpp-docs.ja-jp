---
description: '詳細情報: かっこ付きのファイル名を含む'
title: かっこ付きのファイル名を含む
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: e54792b5feb7d5419896641c25a4367e97d80977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182048"
---
# <a name="including-bracketed-filenames"></a>かっこ付きのファイル名を含む

**ANSI 3.8.2** インクルード可能なソース ファイルを見つけるための手段

山かっこで囲まれたファイル指定の場合、プリプロセッサは親ファイルのディレクトリを検索しません。 "親" ファイルとは、[#include](../preprocessor/hash-include-directive-c-cpp.md) ディレクティブがあるファイルです。 代わりに、コンパイラ コマンド ラインで /I の後に指定したディレクトリからファイル検索を開始します。 /I オプションがない場合または失敗した場合、プリプロセッサは INCLUDE 環境変数を使用して、山かっこで囲まれたインクルード ファイルを検索します。 INCLUDE 環境変数には、セミコロン ( **;** ) で区切られた複数のパスを含めることができます。 複数のディレクトリが /I オプションの一部として、または INCLUDE 環境変数内にある場合、プリプロセッサではそれらのディレクトリを表示されている順序で検索します。

## <a name="see-also"></a>関連項目

[プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
