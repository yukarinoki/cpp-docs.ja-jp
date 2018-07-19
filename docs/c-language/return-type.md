---
title: 戻り値の型 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18d90604ccaebab2d3ed7812835c711d4d56995a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390188"
---
# <a name="return-type"></a>戻り値の型
関数の戻り値の型は、関数によって返される値のサイズと型を規定し、次の構文の type-specifier に相当します。  
  
## <a name="syntax"></a>構文  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* は Microsoft 固有の仕様 */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *type-specifier* には、任意の基本型、構造体型、または共用体型を指定できます。 *type-specifier* が含まれていない場合、戻り値の型は `int` と見なされます。  
  
 関数定義で指定された戻り値の型は、プログラムの別の場所に出現する関数宣言の戻り値の型と一致する必要があります。 関数は、式を含む `return` ステートメントを実行したときに値を返します。 この式が評価され、必要に応じて戻り値の型に変換されて、関数が呼び出されたポイントに返されます。 関数が戻り値の型 `void` で宣言されている場合、式を含む return ステートメントで警告が生成され、式は評価されません。  
  
 次の例に、関数の戻り値を示します。  
  
```  
typedef struct    
{  
    char name[20];  
    int id;  
    long class;  
} STUDENT;  
  
/* Return type is STUDENT: */  
  
STUDENT sortstu( STUDENT a, STUDENT b )  
{  
    return ( (a.id < b.id) ? a : b );  
}  
```  
  
 この例では、`STUDENT` 宣言付きで `typedef` 型を定義し、関数 `sortstu` を、戻り値の型が `STUDENT` になるように定義しています。 この関数は、2 つの構造体引数の 1 つを選択して返します。 その後の関数呼び出しでは、コンパイラは引数の型が `STUDENT` であることを確認します。  
  
> [!NOTE]
>  構造体全体ではなく構造体へのポインターを渡すことによって効率が向上します。  
  
```  
char *smallstr( char s1[], char s2[] )  
{  
    int i;  
  
    i = 0;  
    while ( s1[i] != '\0' && s2[i] != '\0' )  
        i++;  
    if ( s1[i] == '\0' )  
        return ( s1 );  
    else  
        return ( s2 );  
}  
```  
  
 この例では、文字の配列へのポインターを返す関数を定義します。 この関数は 2 つの文字配列 (文字列) を引数として受け取り、2 つの文字列の短い方へのポインターを返します。 配列へのポインターは配列要素の先頭を指し、その型を持つため、この関数の戻り値の型は `char` 型へのポインターになっています。  
  
 `int` の戻り値型を持つ関数は、呼び出し前に宣言する必要はありませんが、引数と戻り値の正しい型チェックができるように、プロトタイプをお勧めします。  
  
## <a name="see-also"></a>参照  
 [C 関数の定義](../c-language/c-function-definitions.md)