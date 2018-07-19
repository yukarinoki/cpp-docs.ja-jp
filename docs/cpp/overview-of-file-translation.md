---
title: ファイル変換の概要 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dd4643c21ebb8626252230b90880af9f9499c0d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943197"
---
# <a name="overview-of-file-translation"></a>ファイル変換の概要
C++ プログラムは、C プログラムと同様、1 つ以上のファイルで構成されます。 これらの各ファイルは、次の概念的な順序で変換されます (実際の順序は "as if" 規則に従います。つまり、変換は、これらの手順に従ったかのように行われる必要があります)。  
  
1. 構文のトークン化。 文字の対応付けとトライグラフ処理、行スプライス、およびトークン化は、この変換フェーズで実行されます。  
  
2. プリプロセス。 この変換フェーズでによって参照される補助ソース ファイルは`#include`ディレクティブでは、「文字列化」と"charizing"ディレクティブを処理し、トークン連結およびマクロの展開を実行します (を参照してください[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)*プリプロセッサ リファレンス*詳細については)。 プリプロセス フェーズの結果、まとまって「翻訳単位」を定義する一連のトークンができます。  
  
     プリプロセッサ ディレクティブは、常にシャープ記号で始まります (**#**) 文字 (つまり、行の最初の非空白文字はシャープ記号とあります)。 1 行に 1 つのプリプロセッサ ディレクティブだけを指定できます。 例えば:  
  
    ```cpp 
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3. コード生成。 この変換フェーズでは、プリプロセス フェーズで生成されたトークンを使用してオブジェクト コードを生成します。  
  
     このフェーズでは、ソース コードの構文チェックと意味チェックが実行されます。  
  
 参照してください[変換の段階](../preprocessor/phases-of-translation.md)で、*プリプロセッサ リファレンス*詳細についてはします。  
  
 C++ プリプロセッサは ANSI C プリプロセッサの厳密なスーパーセットですが、いくつかの点が異なります。 以下に、ANSI C と C++ のプリプロセッサのいくつかの相違点を挙げます。  
  
- 単一行コメントがサポートされています。 参照してください[コメント](../cpp/comments-cpp.md)詳細についてはします。  
  
- 1 つの定義済みマクロ`__cplusplus`C++ の場合のみ定義されます。 参照してください[定義済みマクロ](../preprocessor/predefined-macros.md)で、*プリプロセッサ リファレンス*詳細についてはします。  
  
- C プリプロセッサでは、C++ の演算子が認識されません: **.\***、 **-> \***、および`::`します。 参照してください[演算子](../cpp/cpp-built-in-operators-precedence-and-associativity.md)と[式](../cpp/expressions-cpp.md)演算子の詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [構文規則](../cpp/lexical-conventions.md)