---
title: TCHAR を使用します。H データ型の _MBCS コード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- tchar.h
- TCHAR
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text data types [C++]
- generic-text mappings [C++]
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e80ecd123e3fc47705563156e33f46ecd99a0321
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS コードでの TCHAR.H データ型の使用
ときにマニフェスト定数 **_MBCS**は、定義されている、特定の汎用テキスト ルーチンを次のようなルーチンのいずれかにマップします。  
  
-   マルチバイト、文字、文字列を適切に処理する SBCS ルーチン。 この場合、文字列引数は型にする想定**char\*** です。 たとえば、`_tprintf`にマップ`printf`; 文字列引数を`printf`型の**char\*** です。 使用する場合、 **_TCHAR**汎用テキストのデータ型は、文字列型、仮引数と実際のパラメーターの型を`printf`ので一致 **_TCHAR**\*にマップ**char\***.  
  
-   MBCS 固有ルーチン。 この場合、文字列引数は型にする想定`unsigned` **char\*** です。 たとえば、`_tcsrev`にマップ`_mbsrev`が必要ですが、型の文字列を返しますと`unsigned` **char\*** です。 使用する場合、 **_TCHAR**汎用テキストのデータ型の文字列型の競合がある潜在的な型ため **_TCHAR**型にマップ`char`です。  
  
 この型の競合 (および C コンパイラの警告または C++ コンパイラのエラーという結果) を回避するためには、次のような 3 つの解決方法があります。  
  
-   既定の動作を使用します。 Tchar.h では、次の例のように、ランタイム ライブラリ ルーチンの汎用テキスト ルーチンのプロトタイプを提供します。  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     既定では、プロトタイプ`_tcsrev`にマップ`_mbsrev`Libc.lib 内のサンクをします。 これにより、変更の種類、`_mbsrev`パラメーターと出力方向の受信からの戻り値 **_TCHAR \***  (つまり、 `char` **\***) に`unsigned``char` **\***. この方法を使用しているときに一致の種類によって、 **_TCHAR**は、関数呼び出しのオーバーヘッドにより比較的遅くなります。  
  
-   コードに次のプリプロセッサ ステートメントを組み込むことにより、関数のインライン展開を使用します。  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     このメソッドに適切な MBCS ルーチンに直接の汎用テキスト ルーチンのマップ、Tchar.h で提供される、インライン関数サンクをによりします。 Tchar.h から次のコードの抜粋では、これを行う方法の例を示します。  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     インライン展開を使用できる場合は、この方法が最適な解決法になります。確実に型が一致し、追加の時間コストが発生しないからです。  
  
-   コードで次のプリプロセッサ ステートメントを組み込むことにより、直接マッピングを使用します。  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     この方法は、既定の動作を使用したくない場合、またはインライン展開を使用できない場合の代替手段であり、高速です。 Tchar.h から次の例のように、そのルーチンの MBCS バージョンに直接マクロでマップする汎用テキスト ルーチンが行われます。  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     この方法を採用する場合は、文字列の引数と戻り値の文字列の適切なデータ型の使用を確認するように注意する必要があります。 適切に型を一致させるために型キャストを使用できます。または、汎用テキストのデータ型である **_TXCHAR** を使用できます。 **または _TXCHAR**型にマップ`char`SBCS コードが型にマップ`unsigned` `char` MBCS コードにします。 汎用テキストのマクロの詳細については、次を参照してください。[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [Tchar.h における汎用テキストのマッピング](../text/generic-text-mappings-in-tchar-h.md)