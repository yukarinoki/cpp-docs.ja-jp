---
title: かっこ付きのファイル名を含む | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ba45c21029a428784e1c8410dcf42295aa6350f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383827"
---
# <a name="including-bracketed-filenames"></a>かっこ付きのファイル名を含む
**ANSI 3.8.2** インクルード可能なソース ファイルを見つけるための手段  
  
 山かっこで囲まれたファイル指定の場合、プリプロセッサは親ファイルのディレクトリを検索しません。 "親" ファイルとは、[#include](../preprocessor/hash-include-directive-c-cpp.md) ディレクティブがあるファイルです。 代わりに、コンパイラ コマンド ラインで /I の後に指定したディレクトリからファイル検索を開始します。 /I オプションがない場合または失敗した場合、プリプロセッサは INCLUDE 環境変数を使用して、山かっこで囲まれたインクルード ファイルを検索します。 INCLUDE 環境変数には、セミコロン (**;**) で区切られた複数のパスを含めることができます。 複数のディレクトリが /I オプションの一部として、または INCLUDE 環境変数内にある場合、プリプロセッサではそれらのディレクトリを表示されている順序で検索します。  
  
## <a name="see-also"></a>参照  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)