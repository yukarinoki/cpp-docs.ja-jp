---
title: execution_character_set |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
dev_langs:
- C++
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6cb84ae6ffebda3dd335bc001463e2d8579f99
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="executioncharacterset"></a>execution_character_set
文字列リテラルおよび文字リテラルの使用、実行文字セットを指定します。 このディレクティブは、u8 プレフィックスでマークされたリテラルの場合は不要です。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma execution_character_set("target")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `target`  
 ターゲット実行文字セットを指定します。 現在サポートされている設定だけのターゲットの実行は"utf-8"です。  
  
## <a name="remarks"></a>コメント  
 このコンパイラ ディレクティブは、Visual Studio 2015 Update 2 以降今後使用しません。 使用することをお勧め、 **/execution-charset:utf-8**または **/utf-8**コンパイラ オプションを使用すると共に、`u8`ナロー文字リテラルと文字列リテラルを含む拡張でのプレフィックス文字があります。 詳細については、`u8`プレフィックスを参照してください[文字列リテラルと文字リテラル](../cpp/string-and-character-literals-cpp.md)です。 コンパイラ オプションの詳細については、次を参照してください。 [(設定実行文字セット)/execution-charset](../build/reference/execution-charset-set-execution-character-set.md)と[/utf-8 (ソースの設定および実行可能ファイルの文字セットを utf-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)です。  
  
 `#pragma execution_character_set("utf-8")`ディレクティブ ナロー文字と、ソース コード内のナロー文字列リテラルを実行可能ファイルで utf-8 としてエンコードするコンパイラに指示します。 この出力のエンコードは、使用するソース ファイルのエンコーディングの依存しません。  
  
 既定では、コンパイラは、実行文字セットと現在のコード ページを使用して、ナロー文字とナロー文字列をエンコードします。 これは、Unicode 文字または DBCS 文字リテラルには現在のコード ページの範囲外にあるが、出力に既定の置換文字に変換されることを意味します。 Unicode と DBCS 文字は、その下位バイトに切り捨てられます。 これは、ほぼ確実に望ましくないです。 Utf-8 エンコーディングを使用して、ソース ファイル内のリテラルを指定することができます、`u8`プレフィックス。 コンパイラは、変更されずに出力に utf-8 でエンコードされた文字列を渡します。 U8 プレフィックス ナロー文字リテラルが 1 つのバイトに収まる必要があります。 または出力が切り捨てられます。  
  
 既定では、Visual Studio は、出力のソース コードの解釈に使用するソース文字セットとして現在のコード ページを使用します。 ファイルが読み込まれると、Visual Studio の解釈が現在のコード ページに従ってか、バイト順マーク (BOM) または utf-16 文字が検出されている場合、ファイルの先頭に、ファイルのコード ページが設定された場合を除きです。 自動検出が BOM なしの utf-8 としてエンコードされたソース ファイルを検出すると、現在のコード ページと utf-8 を設定できない、ため Visual Studio では、現在のコード ページを使用してエンコードされます。 範囲の指定された、または自動的に検出されるコード ページは、コンパイラの警告とエラーが発生することができます、ソース ファイル内の文字をします。  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと _ _pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/execution-charset (設定実行文字セット)](../build/reference/execution-charset-set-execution-character-set.md)   
 [/utf-8 (ソースと実行可能ファイルの文字セットを UTF-8 に設定する)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)