---
title: TCHAR を使用します。_MBCS コードでデータ型を H |Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 445e4c9e5c3c7a71d527b6a378cad9e1d767354a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604732"
---
# <a name="using-tcharh-data-types-with-mbcs-code"></a>_MBCS コードでの TCHAR.H データ型の使用
ときに、マニフェスト定数`_MBCS`が定義されている、指定した汎用テキスト ルーチンには次のようなルーチンのいずれかにマップします。  
  
-   マルチバイト、文字、文字列を適切に処理する SBCS ルーチン。 この場合、文字列引数は `char*` 型であることを想定しています。 たとえば、`_tprintf` は `printf` にマップされ、`printf` への文字列引数は `char*` 型になります。 文字列型として汎用テキストのデータ型である `_TCHAR` を使用する場合、`_TCHAR*` は `char*` にマップされるため `printf` の仮パラメーターと実パラメーターの型は一致します。  
  
-   MBCS 固有ルーチン。 この場合、文字列引数は `unsigned char*` 型であることを想定しています。 たとえば、`_tcsrev` は、`unsigned char*` 型の文字列を必要とし、それを返す `_mbsrev` にマップされます。 使用する場合、`_TCHAR`型が競合する可能性があるためですが、文字列型の汎用テキストのデータ型`_TCHAR`型にマップ`char`します。  
  
 この型の競合 (および C コンパイラの警告または C++ コンパイラのエラーという結果) を回避するためには、次のような 3 つの解決方法があります。  
  
-   既定の動作を使用します。 Tchar.h では、次の例のように、ランタイム ライブラリのルーチンに対して汎用テキスト ルーチンのプロトタイプを提供します。  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     既定では、プロトタイプを`_tcsrev`マップ`_mbsrev`Libc.lib のサンクを介してします。 これにより、変更の種類、`_mbsrev`受信パラメーターと出力方向からの値を返します`_TCHAR*`(つまり、 `char *`) に`unsigned char *`します。 このメソッドを使用する場合に一致する種類を確認する`_TCHAR`が、関数呼び出しのオーバーヘッドにより比較的低速になります。  
  
-   コードに次のプリプロセッサ ステートメントを組み込むことにより、関数のインライン展開を使用します。  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     このメソッドは、汎用テキスト ルーチンを適切な MBCS ルーチンに直接マップ、Tchar.h で提供される、インライン関数サンクをによりします。 Tchar.h から次のコードの抜粋では、これを行う方法の例を示します。  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     インライン展開を使用できる場合は、この方法が最適な解決法になります。確実に型が一致し、追加の時間コストが発生しないからです。  
  
-   コードに次のプリプロセッサ ステートメントを組み込むことにより、直接のマッピングを使用します。  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     この方法は、既定の動作を使用したくない場合、またはインライン展開を使用できない場合の代替手段であり、高速です。 汎用テキスト ルーチンがマクロによって Tchar.h から次の例のように、そのルーチンの MBCS バージョンに直接マップするとします。  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     この方法で実行する場合は、必ず適切なデータ型の文字列引数と文字列の戻り値の使用を確認してする必要があります。 適切に型を一致させるために型キャストを使用できます。または、汎用テキストのデータ型である `_TXCHAR` を使用できます。 `_TXCHAR` 型にマップ**char**型にマップされますが SBCS コードで**unsigned char** MBCS コードでします。 汎用テキストのマクロの詳細については、次を参照してください。[汎用テキスト マッピング](../c-runtime-library/generic-text-mappings.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="see-also"></a>関連項目  
 [Tchar.h における汎用テキストのマッピング](../text/generic-text-mappings-in-tchar-h.md)