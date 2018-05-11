---
title: extern ストレージ クラス指定子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a578514aaf6de4132bd856900b0ec31d31835c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="extern-storage-class-specifier"></a>extern ストレージ クラス指定子
`extern` のストレージ クラス指定子で宣言された変数は、プログラムのソース ファイルのいずれかの外部レベルで定義されている同じ名前の変数への参照です。 内部 `extern` 宣言は、ブロック内で外部レベル変数定義を表示するために使用されます。 外部レベルで宣言されていない限り、`extern` キーワードを使用して宣言された変数は、宣言されたブロックでのみ使用できます。  
  
## <a name="example"></a>例  
 この例では、内部および外部レベルの宣言を示しています。  
  
```  
// extern_StorageClassSpecified.c  
#include <stdio.h>  
  
void other( void );  
  
int main()  
{  
    // Reference to i, defined below:   
    extern int i;  
  
    // Initial value is zero; a is visible only within main:   
    static int a;  
  
    // b is stored in a register, if possible:   
    register int b = 0;  
  
    // Default storage class is auto:   
    int c = 0;  
  
    // Values printed are 1, 0, 0, 0:   
    printf_s( "%d\n%d\n%d\n%d\n", i, a, b, c );  
    other();  
    return;  
}  
  
int i = 1;  
  
void other( void )  
{  
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;  
  
    // i is redefined; global i no longer visible:   
    int i = 16;  
  
    // This a is visible only within the other function:   
    static int a = 2;  
  
    a += 2;  
    // Values printed are 16, 4, and 1:  
    printf_s( "%d\n%d\n%d\n", i, a, *external_i );  
}  
```  
  
 この例では、変数 `i` は初期値 1 の外部レベルで定義されます。 `extern` 関数内の `main` 宣言は、外部レベル `i` への参照を宣言するために使用されます。 初期化子は省略されるため、**static** 変数 `a` は、既定で 0 に初期化されます。 `printf` の呼び出しにより、値 1、0、0、および 0 が出力されます。  
  
 `other` 関数では、**static** ポインター変数 `external_i` を初期化するために、グローバル変数 `i` のアドレスが使用されます。 グローバル変数の有効期間が **static** である、つまりプログラム実行中にアドレスが変わることがないので、これは機能します。 次に、変数 `i` は、初期値 16 を持つローカル変数として再定義されます。 この再定義は、ローカル変数用にその名前が使用されていることによって隠されている外部レベルの `i` の値には影響しません。 グローバル `i` の値には、ポインター `external_i` を通じて、このブロック内で間接的な方法でのみアクセスできるようになりました。 ポインターに **auto** 変数 `i` のアドレスを割り当てようとしましたが、ブロックが入力されるたびに異なる可能性があるため機能しません。 変数 `a` は **static** 変数として宣言され、2 に初期化されます。 内部レベルの **static** 変数は宣言されているブロック内でのみ表示されるため、`a` は `main` の `a` と競合しません。  
  
 変数 `a` は 2 だけ増加し、結果は 4 です。 `other` 関数が同じプログラムで再び呼び出される場合、`a` の初期値は 4 になります。 内部**静的**変数は、プログラムが終了したときに値を保持し、値を保持したまま、宣言されているブロックに入ります。  
  
## <a name="see-also"></a>参照  
 [内部レベル宣言のストレージ クラス指定子](../c-language/storage-class-specifiers-for-internal-level-declarations.md)